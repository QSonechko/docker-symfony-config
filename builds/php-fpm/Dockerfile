FROM php:5.6-fpm

ADD php.ini /usr/local/etc/php/conf.d/

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN apt-get update && apt-get install zip unzip -y

RUN docker-php-ext-install pdo
RUN docker-php-ext-install pdo_mysql

RUN yes | pecl install xdebug
ADD xdebug.ini /usr/local/etc/php/conf.d/

RUN wget https://phar.phpunit.de/phpunit.phar
RUN chmod +x phpunit.phar
RUN sudo mv phpunit.phar /usr/local/bin/phpunit