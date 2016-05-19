FROM php:5.6-apache
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        zziplib-bin \
        zlib1g-dev \
    && docker-php-ext-install iconv mcrypt pdo pdo_mysql mysqli zip \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd
RUN apt-get update && apt-get install -y \
        php5-gd \
        php5-curl \
        php5-mcrypt \
        php5-mysql \
        php5-intl
RUN a2enmod rewrite
RUN usermod -u 1000 www-data
RUN usermod -G staff www-data

