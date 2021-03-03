# env-laravel 🐳

![License](https://img.shields.io/github/license/sosobl/env-laravel)
![Stars](https://img.shields.io/github/stars/sosobl/env-laravel)
![Issues](https://img.shields.io/github/issues/sosobl/env-laravel)
![Forks](https://img.shields.io/github/forks/sosobl/env-laravel)

## Introduction

- Build a simple laravel development environment with docker-compose.
- fork from [ucan-lab/docker-laravel](https://github.com/ucan-lab/docker-laravel)

## References

- [最強のLaravel開発環境をDockerを使って構築する](https://qiita.com/ucan-lab/items/5fc1281cd8076c8ac9f4)
- [DockerでPHP7.4+Apache+MySQLの環境構築しようと思ったら詰まりまくった【Windows & Mac】](https://qiita.com/buzzdark1212/items/b542161523aa324d9c3d)

## Usage

- with creating laravel project

    ```bash
    $ git clone git@github.com:sosobl/env-laravel.git
    $ cd env-laravel
    $ make create-project # Install the latest Laravel project
    $ make install-recommend-packages # Not required
    ```

- without creating laravel project

    ```bash
    $ git clone git@github.com:sosobl/env-laravel.git
    $ cd env-laravel
    $ git clone git@github.com:laravel/laravel.git docker-laravel/backend # Clone any project to the backend directory
    $ make init
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
