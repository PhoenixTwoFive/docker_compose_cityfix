#PHP und Apache
FROM php:7.1-apache
COPY ./apache2.conf /etc/apache2/apache2.conf

#Abhängigkeiten von lumen
RUN docker-php-ext-install pdo
RUN docker-php-ext-install mbstring

#Xdebug
RUN pecl install xdebug-2.5.5 \
    && docker-php-ext-enable xdebug

# phpunit
ADD https://phar.phpunit.de/phpunit.phar /tmp/
RUN chmod +x /tmp/phpunit.phar && \
    mv /tmp/phpunit.phar /usr/local/bin/phpunit && \
    phpunit --version

RUN a2enmod rewrite headers setenvif

COPY ./000-default.conf /etc/apache2/sites-available/000-default.conf