FROM php:8.2-fpm
ENV DEBIAN_FRONTEND noninteractive
 
 RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install \
        --no-install-recommends \
        --fix-missing \
        --assume-yes \
            libxml2-dev libcurl4-gnutls-dev libonig-dev && \
    apt-get clean autoclean && \
    apt-get autoremove && \
    rm -rf /var/lib/{apt,dpkg,cache,log} /tmp/* /var/tmp/*

RUN docker-php-ext-install \
    opcache \
    #mbstring \
    #xml \
    intl \
    #json \
    #curl \
    #fileinfo \
    pcntl