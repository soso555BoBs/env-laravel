# docker-laravel 🐳

![License](https://img.shields.io/github/license/sosobl/env-laravel?color=f05340)
![Stars](https://img.shields.io/github/stars/sosobl/env-laravel?color=f05340)
![Issues](https://img.shields.io/github/issues/sosobl/env-laravel?color=f05340)
![Forks](https://img.shields.io/github/forks/sosobl/env-laravel?color=f05340)

## Introduction

Build a simple laravel development environment with docker-compose.
fork from ![ucan-lab/docker-laravel](https://github.com/ucan-lab/docker-laravel)

## Usage

```bash
$ git clone git@github.com:sosobl/env-laravel.git
$ cd env-laravel
$ make create-project # Install the latest Laravel project
$ make install-recommend-packages # Not required
```

http://localhost

Read this [Makefile](https://github.com/sosobl/env-laravel/blob/master/Makefile).

## Tips

Read this [Wiki](https://github.com/sosobl/env-laravel/wiki).

## Container structure

```bash
├── app
└── db
```

### app container

- Base image
  - [php](https://hub.docker.com/_/php):7.4-apache
  - [composer](https://hub.docker.com/_/composer):2.0

### db container

- Base image
  - [mysql](https://hub.docker.com/_/mysql):8.0

#### Persistent MySQL Storage

By default, the [named volume](https://docs.docker.com/compose/compose-file/#volumes) is mounted, so MySQL data remains even if the container is destroyed.
If you want to delete MySQL data intentionally, execute the following command.

```bash
$ docker-compose down -v && docker-compose up
```
