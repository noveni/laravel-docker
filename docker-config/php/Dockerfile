FROM php:7.0.1-fpm
RUN apt-get update && apt-get install -y \
                                apt-utils \
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install mbstring
RUN apt-get install -y libxslt-dev
RUN docker-php-ext-install xsl
RUN docker-php-ext-install xmlrpc



COPY config/php.ini /usr/local/etc/php/
COPY config/conf.d/opcache-recommended.ini /usr/local/etc/php/conf.d/
WORKDIR /usr/local/apache2/htdocs/

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin/ --filename=composer
