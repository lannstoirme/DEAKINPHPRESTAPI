FROM php:5.6-apache

COPY php.ini /usr/local/etc/php/
RUN apt-get update && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng12-dev libmcrypt-dev mysql-client \
&& docker-php-ext-install pdo_mysql msqli gd iconv \
&& docker-php-ext-install mbstring \
&& docker-php-ext-install mcrypt

COPY ./phpsite.com.conf    /etc/apache2/sites-available/
COPY ./hosts /etc/hosts
RUN a2enmod rewrite

#RUN a2endmod mcrypt
RUN service apache2 restart
WORKDIR /etc/apache2/sites-available/
RUN a2ensite blogsite.com.conf

EXPOSE 80