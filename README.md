# Docker Nginx PHP Example

[![Software License][ico-license]](LICENSE.md)

This is a simple example for running a docker container with php and nginx.

## Get it up and running

- [Install docker on your machine.](install-docker)

- [Install docker-compose on your machine.](install-docker-compose)

- Clone this repository.

``` bash
$ git clone https://github.com/mhilker/docker-nginx-php-example
```

- Switch to the cloned directory.

``` bash
$ cd docker-nginx-php-example
```

- Start the stack.

``` bash
$ docker-compose up
```

- You should see an output like this.

``` bash
$ docker-compose up --build
Building php
Step 1/4 : FROM php:7.1-fpm-alpine
 ---> 8a87fcbea0c9
Step 2/4 : COPY ./conf/php-fpm.conf /etc/php/7.1/fpm/pool.d/www.conf
 ---> Using cache
 ---> 3b0231129196
Step 3/4 : COPY ./src/ /code
 ---> Using cache
 ---> 25dedd6a97c0
Step 4/4 : VOLUME /code
 ---> Using cache
 ---> 55ce4a7c4581
Successfully built 55ce4a7c4581
Successfully tagged dockernginxphpexample_php:latest
Building web
Step 1/2 : FROM nginx:1.11-alpine
 ---> f35b49deb234
Step 2/2 : COPY ./conf/nginx.conf /etc/nginx/conf.d/default.conf
 ---> Using cache
 ---> fc1acee77b45
Successfully built fc1acee77b45
Successfully tagged dockernginxphpexample_web:latest
Starting dockernginxphpexample_php_1
Starting dockernginxphpexample_web_1
Attaching to dockernginxphpexample_php_1, dockernginxphpexample_web_1
php_1  | [19-May-2017 21:44:03] NOTICE: fpm is running, pid 1
php_1  | [19-May-2017 21:44:03] NOTICE: ready to handle connections
```

- Visit `localhost:8080` in your browser.


## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[install-docker]: https://docs.docker.com/engine/installation
[install-docker-compose]: https://docs.docker.com/compose/install
