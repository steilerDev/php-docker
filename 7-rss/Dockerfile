FROM docker.steilergroup.net/php:7-mysql-gd

RUN apt-get update \
    && apt-get install \
        --no-install-recommends \
        --fix-missing \
        --assume-yes \
            libxml2-dev libcurl4-gnutls-dev libonig-dev && \
        rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
 
RUN docker-php-ext-install opcache mbstring xml intl json curl fileinfo pcntl
