FROM php:5.6-fpm

ADD php.ini /usr/local/etc/php/conf.d/

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN apt-get update && \
    apt-get install zip unzip wget -y && \
    docker-php-ext-install pdo && \
    docker-php-ext-install pdo_mysql && \
    yes | pecl install xdebug

ADD xdebug.ini /usr/local/etc/php/conf.d/

RUN wget https://phar.phpunit.de/phpunit.phar && \
    chmod +x phpunit.phar && \
    mv phpunit.phar /usr/local/bin/phpunit
