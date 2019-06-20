FROM php:7-fpm
RUN apt-get update && apt-get install -y \
  libfreetype6-dev libjpeg62-turbo-dev libmcrypt-dev \
  git vim unzip \
  && docker-php-ext-install pdo_mysql mysqli mbstring gd iconv \
  && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
  && docker-php-ext-install -j$(nproc) gd \
  && apt-get clean
COPY ./php.ini /usr/local/etc/php/