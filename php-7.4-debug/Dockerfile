FROM php:7.4-fpm

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    git \
    libzip-dev \
    zip \
    unzip

RUN docker-php-ext-configure \
    zip --with-libzip \
    && docker-php-ext-install \
    pdo \
    pdo_mysql \
    zip

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && echo "xdebug.start_with_request=yes" >> /usr/local/etc/php/conf.d/xdebug.ini \
    && echo 'date.timezone = "Europe/Moscow"\n' > /usr/local/etc/php/conf.d/timezone.ini

RUN curl --silent --show-error https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && mkdir /var/www/.composer \
    && chown www-data:www-data /var/www/.composer

RUN usermod -u 1000 www-data

WORKDIR /var/www/src

CMD ["php-fpm"]
