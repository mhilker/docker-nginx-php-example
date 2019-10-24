FROM php:7.3-fpm-alpine3.10

# Copy the php config file
COPY ./docker/php/php-fpm.conf /etc/php/7.1/fpm/pool.d/www.conf

# Copy the application code
COPY . /code

VOLUME ["/code"]
