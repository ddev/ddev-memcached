[![tests](https://github.com/ddev/ddev-memcached/actions/workflows/tests.yml/badge.svg)](https://github.com/ddev/ddev-memcached/actions/workflows/tests.yml) ![project is maintained](https://img.shields.io/maintenance/yes/2024.svg)

## What is this?

This repository allows you to quickly install Memcached into a [DDEV](https://ddev.readthedocs.io) project using `ddev get ddev/ddev-memcached`.

## Installation

For DDEV v1.23.5 or above run

```sh
ddev add-on get ddev/ddev-memcached && ddev restart
```

For earlier versions of DDEV run

```sh
ddev get ddev/ddev-memcached && ddev restart
```

## Explanation

This Memcached recipe for [DDEV](https://ddev.readthedocs.io) installs a [`.ddev/docker-compose.memcached.yaml`](docker-compose.memcached.yaml) using the `memcached` Docker image.

## Interacting with Memcached

* The Memcached instance will listen on TCP port 11211 (the Memcached default).
* Configure your application to access Memcached on the host:port `memcached:11211`.
* To reach the Memcached admin interface, run `ddev ssh` to connect to the web container, then use `nc` or `telnet` to connect to the Memcached container on port 11211, i.e. `nc memcached 11211`. You can then run commands such as `stats` to see usage information. See [cheatsheet](https://lzone.de/cheat-sheet/memcached) for more commands.
