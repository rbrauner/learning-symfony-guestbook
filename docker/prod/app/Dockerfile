ARG APP_IMAGE_VERSION
FROM ghcr.io/rbrauner/learning-symfony-guestbook-php:${APP_IMAGE_VERSION}

LABEL org.opencontainers.image.source https://github.com/rbrauner/learning-symfony-guestbook
LABEL org.opencontainers.image.description="Learning - Symfony guestbook - App image"
LABEL org.opencontainers.image.licenses=MIT

RUN apk update
RUN apk upgrade

# Custom cache invalidation
ARG CACHEBUST=1

# initialize project
RUN git clone https://github.com/rbrauner/learning-symfony-guestbook.git .
RUN mkdir -p data/database-data var
RUN chmod 777 var
RUN echo "APP_ENV=prod" > .env.local
RUN symfony composer install
