FROM php:7.2.0-apache
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
        zziplib-bin \
        zlib1g-dev \
    && docker-php-ext-install iconv pdo pdo_mysql mysqli zip \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd \
    && rm -rf /var/lib/apt/lists/*

RUN a2enmod rewrite \
&& usermod -u 1000 www-data \
&& usermod -G staff www-data

