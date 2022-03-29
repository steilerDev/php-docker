FROM php:8.1-fpm
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

RUN docker-php-ext-install pdo pdo_pgsql pgsql pdo_mysql gd opcache intl pcntl zip exif