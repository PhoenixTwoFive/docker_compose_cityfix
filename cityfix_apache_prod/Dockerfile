#PHP und Apache
FROM php:7.1-apache
COPY ./apache2.conf /etc/apache2/apache2.conf


#Abhängigkeiten von lumen
RUN docker-php-ext-install pdo
RUN docker-php-ext-install mbstring

RUN a2enmod rewrite headers setenvif
RUN a2enmod proxy
RUN a2enmod proxy_http
RUN a2enmod lbmethod_byrequests


COPY ./000-default.conf /etc/apache2/sites-available/000-default.conf