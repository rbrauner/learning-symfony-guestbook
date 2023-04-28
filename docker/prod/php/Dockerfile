ARG PHP_VERSION
FROM php:${PHP_VERSION}

LABEL org.opencontainers.image.source https://github.com/rbrauner/learning-symfony-guestbook
LABEL org.opencontainers.image.description="Learning - Symfony guestbook - PHP image"
LABEL org.opencontainers.image.licenses=MIT

RUN apk update
RUN apk upgrade
RUN apk add bash git

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

RUN install-php-extensions intl

RUN install-php-extensions zip

RUN install-php-extensions gd

RUN install-php-extensions imagick

RUN install-php-extensions pdo_pgsql

RUN install-php-extensions xsl

RUN install-php-extensions redis

RUN install-php-extensions amqp

RUN install-php-extensions opcache

RUN install-php-extensions apcu

# RUN install-php-extensions xdebug

# composer
RUN install-php-extensions @composer

# symfony cli
RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.alpine.sh' | bash \
    && apk add symfony-cli

# copy config
COPY ./php.ini /usr/local/etc/php/php.ini

# initialize project
RUN git clone https://github.com/rbrauner/learning-symfony-guestbook.git .
RUN mkdir -p data var var/database-data
RUN echo "APP_ENV=prod" > .env.local
RUN symfony composer install
