ARG PHP_IMAGE_VERSION
FROM php:${PHP_IMAGE_VERSION}

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

RUN install-php-extensions xdebug

# composer
RUN install-php-extensions @composer

# symfony cli
RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.alpine.sh' | bash \
    && apk add symfony-cli
