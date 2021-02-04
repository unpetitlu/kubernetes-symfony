FROM php:7.4-fpm

RUN apt-get update && apt-get install -y \
    git \
    unzip

RUN curl --insecure https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer
RUN composer self-update

RUN docker-php-ext-install pdo pdo_mysql

COPY docker/php/custom-php.ini /usr/local/etc/php/conf.d/custom.ini

WORKDIR /usr/src/app

COPY . .
