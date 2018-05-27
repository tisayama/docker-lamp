FROM php:5.6-apache
COPY php.ini /usr/local/etc/php/
ARG WEBROOT

RUN apt-get update \
  && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev libmcrypt-dev \
  && docker-php-ext-install pdo_mysql mysqli mbstring gd iconv mcrypt

RUN sed -i -e"s%/var/www/html%${WEBROOT}%" /etc/apache2/sites-available/000-default.conf
WORKDIR ${WEBROOT}
