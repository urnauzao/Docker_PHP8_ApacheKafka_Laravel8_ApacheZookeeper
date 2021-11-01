ARG PHP_VERSION=8.0.12-fpm
FROM php:${PHP_VERSION}

RUN apt-get update && apt-get install -y net-tools nano
RUN apt-get install -y libpq-dev libxml2-dev \
    zlib1g-dev \
    libzip-dev \
    unzip \
    libpng-dev

#RUN apt-get install -y --no-install-recommends supervisor
#COPY supervisord.conf /etc/supervisor
#COPY supervisord/conf /etc/supervisord.d/

#RUN docker-php-ext-install mysqli
#RUN docker-php-ext-install pdo
#RUN docker-php-ext-install pdo_mysql
#RUN docker-php-ext-install pdo_pgsql
#RUN docker-php-ext-install pgsql
#RUN docker-php-ext-install session
#RUN docker-php-ext-install xml
#RUN docker-php-ext-install iconv
#RUN docker-php-ext-install simplexml
#RUN docker-php-ext-install pcntl
#RUN docker-php-ext-install zip
#RUN docker-php-ext-install gd
RUN docker-php-ext-install mysqli pdo pdo_mysql pdo_pgsql pgsql session xml zip iconv simplexml pcntl gd

RUN docker-php-ext-configure gd

RUN pecl install redis-5.3.4 \
    && docker-php-ext-enable redis 

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# instalar rdkafka

RUN apt install librdkafka-dev -y \ 
    && pecl install rdkafka \ 
    && docker-php-ext-enable rdkafka

RUN apt-get clean
RUN rm -rf var/www/*
# CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/supervisord.conf"]
EXPOSE 9000 9001