FROM php:8.0-apache

RUN a2enmod rewrite

RUN apt-get update && apt-get install -y git unzip zip

WORKDIR /var/www/html

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/
RUN install-php-extensions gd pdo_mysql bcmath zip intl opcache mbstring

# Install xdebug extension
RUN pecl install xdebug-3.0.0 \
    && docker-php-ext-enable xdebug

RUN a2enmod ssl

COPY --from=composer:2.0 /usr/bin/composer /usr/local/bin/composer

# Install Node.js - uncomment your target version
#RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -
#RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash -
#RUN curl -sL https://deb.nodesource.com/setup_16.x | bash -
RUN apt-get install -y nodejs
RUN echo "NODE Version:" && node --version
RUN echo "NPM Version:" && npm --version
RUN npm i -g nodemon
RUN echo "NODEMON Version:" && nodemon --version
