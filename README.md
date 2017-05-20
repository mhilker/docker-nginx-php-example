# Docker Nginx PHP Example

[![Software License][ico-license]](LICENSE.md)

This is a simple example for running a docker container with php and nginx.

## Get it up and running

- [Install docker on your machine.][install-docker]

- [Install docker-compose on your machine.][install-docker-compose]

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
$docker-compose up --build
Building php
Step 1/4 : FROM php:7.1-fpm-alpine
 ---> 8a87fcbea0c9
Step 2/4 : COPY ./conf/php-fpm.conf /etc/php/7.1/fpm/pool.d/www.conf
 ---> Using cache
 ---> 3b0231129196
Step 3/4 : COPY . /code
 ---> 4e862a5bae65
Removing intermediate container eb4c8aa38fd6
Step 4/4 : VOLUME /code
 ---> Running in 965b923d1612
 ---> a48844bbb0f9
Removing intermediate container 965b923d1612
Successfully built a48844bbb0f9
Successfully tagged dockernginxphpexample_php:latest
Building web
Step 1/2 : FROM nginx:1.11-alpine
 ---> f35b49deb234
Step 2/2 : COPY ./conf/nginx.conf /etc/nginx/conf.d/default.conf
 ---> 906659bc675e
Removing intermediate container d024ec3e3a48
Successfully built 906659bc675e
Successfully tagged dockernginxphpexample_web:latest
Recreating dockernginxphpexample_php_1
Recreating dockernginxphpexample_web_1
Attaching to dockernginxphpexample_php_1, dockernginxphpexample_web_1
php_1  | [20-May-2017 19:27:58] NOTICE: fpm is running, pid 1
php_1  | [20-May-2017 19:27:58] NOTICE: ready to handle connections
```

- Visit `localhost:8080` in your browser. You should see an output like this.

![Hello World Output with Docker and PHP + Nginx](./resources/screenshot-01.png)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[install-docker]: https://docs.docker.com/engine/installation
[install-docker-compose]: https://docs.docker.com/compose/install
