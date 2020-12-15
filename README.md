# docker-laravel-apache 🐳

![License](https://img.shields.io/github/license/ucan-lab/docker-laravel-apache?color=f05340)
![Stars](https://img.shields.io/github/stars/ucan-lab/docker-laravel-apache?color=f05340)
![Issues](https://img.shields.io/github/issues/ucan-lab/docker-laravel-apache?color=f05340)
![Forks](https://img.shields.io/github/forks/ucan-lab/docker-laravel-apache?color=f05340)

## Introduction

Build a simple laravel development environment with docker-compose.
Apache version of [docker-laravel](https://github.com/ucan-lab/docker-laravel).

## Usage

```bash
$ git clone git@github.com:ucan-lab/docker-laravel-apache.git
$ cd docker-laravel-apache
$ make create-project # Install the latest Laravel project
$ make install-recommend-packages # Not required
```

http://localhost

Read this [Makefile](https://github.com/ucan-lab/docker-laravel-apache/blob/master/Makefile).

## Container structure

```bash
├── web
└── db
```

### web container

- Base image
  - [php](https://hub.docker.com/_/php):7.4-apache-buster
  - [composer](https://hub.docker.com/_/composer):2.0
  - [node](https://hub.docker.com/_/node):node:14-buster

### db container

- Base image
  - [mysql](https://hub.docker.com/_/mysql):8.0

#### Persistent MySQL Storage

By default, the [named volume](https://docs.docker.com/compose/compose-file/#volumes) is mounted, so MySQL data remains even if the container is destroyed.
If you want to delete MySQL data intentionally, execute the following command.

```bash
$ docker-compose down -v && docker-compose up
```
