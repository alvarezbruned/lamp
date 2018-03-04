FROM php:5.6.33-apache-jessie
COPY php.ini /usr/local/etc/php/

RUN echo `date`
RUN apt-get update && apt-get upgrade -y \
  && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libmcrypt-dev \
  && docker-php-ext-install pdo_mysql mysqli mbstring gd iconv

RUN apt-get update && apt-get install -y mysql-client && rm -rf /var/lib/apt

ENV TZ="Europe/Madrid"
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN export TZ="Europe/Madrid"

#RUN yes | pecl install xdebug \
#    && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
#    && echo "xdebug.remote_enable=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
#    && echo "xdebug.remote_autostart=off" >> /usr/local/etc/php/conf.d/xdebug.ini
