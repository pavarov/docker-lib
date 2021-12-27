FROM php:8.1.1-fpm-alpine3.15

MAINTAINER pawarow

RUN set -ex \
  && apk --update --no-cache add autoconf g++ make postgresql-dev composer tzdata zip libzip-dev \
  && docker-php-ext-install -j$(nproc) pdo pdo_pgsql zip \
  && pecl install xdebug-3.1.0 \
  && docker-php-ext-enable xdebug \
  && apk del --purge autoconf g++ make

COPY docker-php-ext-xdebug.ini /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini