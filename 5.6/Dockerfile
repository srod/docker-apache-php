FROM php:5.6-apache
MAINTAINER Rodolphe Stoclin <srodolphe@gmail.com>
RUN a2enmod rewrite
# install the PHP extensions we need
RUN apt-get update && rm -rf /var/lib/apt/lists/*
RUN docker-php-ext-install mysqli
RUN echo "date.timezone = Europe/Paris" > /usr/local/etc/php/php.ini
CMD ["apache2-foreground"]
