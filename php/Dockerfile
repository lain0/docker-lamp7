FROM php:7-apache
COPY php.ini /usr/local/etc/php/
RUN apt-get update && \
  apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev libmcrypt-dev \
  && pecl install mcrypt-1.0.2 \
  && mkdir -p /etc/php/7.3/cli/conf.d/ \
  && bash -c "echo extension=$(which mcrypt.so) > /etc/php/7.3/cli/conf.d/mcrypt.ini" \
  && docker-php-ext-install pdo_mysql mysqli mbstring gd iconv mcrypt \
  && docker-php-ext-enable mcrypt
