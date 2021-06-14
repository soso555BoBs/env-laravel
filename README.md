# env-laravel 🐳

![License](https://img.shields.io/github/license/soso555BoBs/env-laravel)
![Stars](https://img.shields.io/github/stars/soso555BoBs/env-laravel)
![Issues](https://img.shields.io/github/issues/soso555BoBs/env-laravel)
![Forks](https://img.shields.io/github/forks/soso555BoBs/env-laravel)

## Introduction

- Build a simple laravel development environment with docker-compose.
- fork from [ucan-lab/docker-laravel](https://github.com/ucan-lab/docker-laravel)

## References

- [最強のLaravel開発環境をDockerを使って構築する](https://qiita.com/ucan-lab/items/5fc1281cd8076c8ac9f4)
- [DockerでPHP7.4+Apache+MySQLの環境構築しようと思ったら詰まりまくった【Windows & Mac】](https://qiita.com/buzzdark1212/items/b542161523aa324d9c3d)
- [npm インストール方法](https://qiita.com/seibe/items/36cef7df85fe2cefa3ea)

## Usage

- with creating laravel project

    ```bash
    $ git clone git@github.com:soso555BoBs/env-laravel.git
    $ cd env-laravel
    $ make create-project # Install the latest Laravel project
    $ make install-recommend-packages # Not required
    ```

- without creating laravel project

    ```bash
    $ git clone git@github.com:soso555BoBs/env-laravel.git
    $ cd env-laravel
    $ git clone git@github.com:laravel/laravel.git docker-laravel/backend # Clone any project to the backend directory
    $ make init
    ```

- http://localhost
- http://localhost:8025/

Read this [Makefile](https://github.com/soso555BoBs/env-laravel/blob/master/Makefile).

## Tips

Read this [Wiki](https://github.com/soso555BoBs/env-laravel/wiki).

## Container structures

```bash
├── app
├── web
├── redis
├── mailhog
└── db
```

### app container

- Base image
  - [php](https://hub.docker.com/_/php):8.0-fpm-buster
  - [composer](https://hub.docker.com/_/composer):2.0

### web container

- Base image
  - [nginx](https://hub.docker.com/_/nginx):1.20-alpine
  - [node](https://hub.docker.com/_/node):16-alpine

### db container

- Base image
  - [mysql/mysql-server](https://hub.docker.com/r/mysql/mysql-server):8.0

#### Persistent MySQL Storage

By default, the [named volume](https://docs.docker.com/compose/compose-file/#volumes) is mounted, so MySQL data remains even if the container is destroyed.
If you want to delete MySQL data intentionally, execute the following command.

```bash
$ docker-compose down -v && docker-compose up
```
