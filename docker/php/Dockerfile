FROM php:7.3-fpm-alpine3.10

# Copy the php config file
COPY ./docker/php/php-fpm.conf /usr/local/etc/php-fpm.d/www.conf

# Copy the application code
COPY . /app

VOLUME ["/app"]
