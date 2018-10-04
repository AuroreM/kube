FROM composer:1.7 as builder

COPY symfony-demo .
RUN composer install

FROM hermsi/alpine-fpm-php:7.2

RUN mkdir /project
COPY symfony-demo /project
RUN mkdir /project/vendor
COPY --from=builder app/vendor /project/vendor
WORKDIR /project