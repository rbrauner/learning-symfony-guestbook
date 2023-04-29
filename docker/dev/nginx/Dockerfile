ARG NGINX_IMAGE_VERSION
FROM nginx:${NGINX_IMAGE_VERSION}

RUN apk update
RUN apk upgrade
RUN apk add openssl bash

ARG PHP_UPSTREAM_CONTAINER=php
ARG PHP_UPSTREAM_PORT=9000

RUN echo "upstream php-upstream { server ${PHP_UPSTREAM_CONTAINER}:${PHP_UPSTREAM_PORT}; }" > /etc/nginx/conf.d/upstream.conf \
    && rm /etc/nginx/conf.d/default.conf

ADD ./startup.sh /opt/startup.sh
RUN sed -i 's/\r//g' /opt/startup.sh
CMD ["/bin/bash", "/opt/startup.sh"]
