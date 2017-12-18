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
    && docker-php-ext-install gd
RUN apt-get update && apt-get install -y \
        php7.0-gd \
        php7.0-curl \
        php7.0-mcrypt \
        php7.0-mysql \
        php7.0-intl
RUN a2enmod rewrite
RUN usermod -u 1000 www-data
RUN usermod -G staff www-data

