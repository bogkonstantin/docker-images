FROM bogkonstantin/php-7.4-debug:latest

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - \
    && apt-get install -y nodejs \
    && npm install -g yarn \
    && mkdir /var/www/.yarn \
    && mkdir /var/www/.cache \
    && touch /var/www/.yarnrc \
    && chown www-data:www-data /var/www/.yarn \
    && chown www-data:www-data /var/www/.yarnrc \
    && chown www-data:www-data /var/www/.cache

RUN usermod -u 1000 www-data

WORKDIR /var/www/src

CMD ["php-fpm"]
