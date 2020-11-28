FROM php:7.4.4-fpm-alpine

ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_HOME /composer

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN apk update && \
    apk --no-cache add \
    curl \
    bash \
    vim \
    icu-dev \
    oniguruma-dev \
    libzip-dev \
    libpng-dev \
    libxml2-dev && \
    # Install php extensions https://book.cakephp.org/4/ja/installation.html
    docker-php-ext-install \
    mbstring \
    intl \
    simplexml \
    bcmath \
    zip \
    pdo_mysql

COPY ./php.ini /usr/local/etc/php/php.ini