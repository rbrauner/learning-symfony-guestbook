ARG POSTGRES_VERSION
FROM postgres:${POSTGRES_VERSION}

LABEL org.opencontainers.image.source https://github.com/rbrauner/learning-symfony-guestbook
LABEL org.opencontainers.image.description="Learning - Symfony guestbook - Database image"
LABEL org.opencontainers.image.licenses=MIT

RUN apk update
RUN apk upgrade
