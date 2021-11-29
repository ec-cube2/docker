FROM php:5.5-apache

# ext-gd: libfreetype6-dev libjpeg62-turbo-dev libpng-dev
# ext-mcrypt: libmcrypt-dev
# ext-pgsql: libpq-dev
# ext-zip: libzip-dev zlib1g-dev
# ext-opcache: libpcre3-dev
RUN apt-get update && apt-get upgrade -y \
    && apt-get install -y \
        git unzip curl apt-transport-https gnupg wget \
        libfreetype6-dev libjpeg62-turbo-dev libpng-dev \
        libmcrypt-dev \
        libpq-dev \
        libzip-dev zlib1g-dev \
        libpcre3-dev \
        ssl-cert \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include --with-jpeg-dir=/usr/include \
    && docker-php-ext-install -j$(nproc) gd mcrypt zip mysql mysqli pgsql opcache
RUN pecl install apcu-4.0.11 && docker-php-ext-enable apcu

# composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php --install-dir=/usr/local/bin --filename=composer \
    && php -r "unlink('composer-setup.php');"

# entrypoint
COPY docker-php-entrypoint /usr/local/bin/

# workdir
WORKDIR /var/www/app

# Enable SSL
RUN a2enmod ssl rewrite headers
EXPOSE 443
