# Docker Nginx PHP Example

[![Software License][ico-license]](LICENSE.md)

This is a simple example for running a docker container with php and nginx.

## Get it up and running

[Install docker on your machine.][install-docker]

[Install docker-compose on your machine.][install-docker-compose]

Clone this repository.

``` bash
$ git clone https://github.com/mhilker/docker-nginx-php-example
```

Switch to the cloned directory.

``` bash
$ cd docker-nginx-php-example
```

Start the stack.

``` bash
$ docker-compose up
```

You should see an output like this.

``` bash
Creating network "docker-nginx-php-example_default" with the default driver
Building php
Step 1/4 : FROM php:7.3-fpm-alpine3.10
 ---> a79798c1245a
Step 2/4 : COPY ./docker/php/php-fpm.conf /usr/local/etc/php-fpm.d/www.conf
 ---> Using cache
 ---> 6275f02538b4
Step 3/4 : COPY . /app
 ---> 53b669adc114
Step 4/4 : VOLUME ["/app"]
 ---> Running in 23a2713774dd
Removing intermediate container 23a2713774dd
 ---> 1395e34b3e6a
Successfully built 1395e34b3e6a
Successfully tagged docker-nginx-php-example_php:latest
Building web
Step 1/2 : FROM nginx:1.17.5-alpine
 ---> b6753551581f
Step 2/2 : COPY ./docker/nginx/nginx.conf /etc/nginx/conf.d/default.conf
 ---> Using cache
 ---> c585192f3f86
Successfully built c585192f3f86
Successfully tagged docker-nginx-php-example_web:latest
Creating docker-nginx-php-example_php_1 ... done
Creating docker-nginx-php-example_web_1 ... done
Attaching to docker-nginx-php-example_php_1, docker-nginx-php-example_web_1
php_1  | [24-Oct-2019 20:12:27] NOTICE: fpm is running, pid 1
php_1  | [24-Oct-2019 20:12:27] NOTICE: ready to handle connections
```

Visit `localhost:8080` in your browser. You should see an output like this.

![Hello World Output with Docker and PHP + Nginx](./resources/screenshot-01.png)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[install-docker]: https://docs.docker.com/engine/installation
[install-docker-compose]: https://docs.docker.com/compose/install
