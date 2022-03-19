FROM docker.steilergroup.net/php:7-mysql

RUN apt-get update \
 && apt-get install \
        --no-install-recommends \
        --fix-missing \
        --assume-yes \
            libpng-dev freetype* && \
        rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
 
RUN docker-php-ext-install gd
