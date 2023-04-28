ARG NGINX_VERSION
FROM nginx:${NGINX_VERSION}

LABEL org.opencontainers.image.source https://github.com/rbrauner/learning-symfony-guestbook
LABEL org.opencontainers.image.description="Learning - Symfony guestbook - Nginx image"
LABEL org.opencontainers.image.licenses=MIT

RUN apk update
RUN apk upgrade
RUN apk add openssl bash

ARG PHP_UPSTREAM_CONTAINER=php
ARG PHP_UPSTREAM_PORT=9000

RUN echo "upstream php-upstream { server ${PHP_UPSTREAM_CONTAINER}:${PHP_UPSTREAM_PORT}; }" > /etc/nginx/conf.d/upstream.conf \
    && rm /etc/nginx/conf.d/default.conf

COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./sites-available/ /etc/nginx/sites-available
RUN mkdir -p /etc/nginx/ssl

ADD ./startup.sh /opt/startup.sh
RUN sed -i 's/\r//g' /opt/startup.sh
CMD ["/bin/bash", "/opt/startup.sh"]
