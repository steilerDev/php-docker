FROM php:8.0-fpm
ENV DEBIAN_FRONTEND noninteractive
 
 RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install \
        --no-install-recommends \
        --fix-missing \
        --assume-yes \
            git rsync libpng-dev freetype* libxml2-dev libcurl4-gnutls-dev libonig-dev libpq-dev libzip-dev && \
    apt-get clean autoclean && \
    apt-get autoremove && \
    rm -rf /var/lib/{apt,dpkg,cache,log} /tmp/* /var/tmp/*

RUN docker-php-ext-install \
    #curl \
    #json \
    #xml \
    #pcre \
    #ctype \
    pdo \
    pdo_pgsql \
    pgsql \
    pdo_mysql \
    gd \
    opcache \
    intl \
    pcntl \
    zip \
    exif

RUN sed 's/\(memory_limit =\) 128M/\1 256M/' $PHP_INI_DIR/php.ini-production \
    > $PHP_INI_DIR/php.ini