ARG DATABASE_IMAGE_VERSION
FROM postgres:${DATABASE_IMAGE_VERSION}

LABEL org.opencontainers.image.source https://github.com/rbrauner/learning-symfony-guestbook
LABEL org.opencontainers.image.description="Learning - Symfony guestbook - Database image"
LABEL org.opencontainers.image.licenses=MIT

RUN apk update
RUN apk upgrade
