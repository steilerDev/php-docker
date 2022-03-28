FROM php:8.1-fpm
ENV DEBIAN_FRONTEND noninteractive
 
 RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install \
        --no-install-recommends \
        --fix-missing \
        --assume-yes \
            libpng-dev freetype* libxml2-dev libcurl4-gnutls-dev libonig-dev libpq-dev && \
    apt-get clean autoclean && \
    apt-get autoremove && \
    rm -rf /var/lib/{apt,dpkg,cache,log} /tmp/* /var/tmp/*

RUN docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql && \
    docker-php-ext-install mysqli pdo pdo_mysql pdo_pgsql gd opcache mbstring xml intl json curl fileinfo pcntl