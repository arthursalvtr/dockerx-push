# DockerX-Push

## Introduction

A simple bash script to push docker image into a given repository

It simply run these following commands:
- `docker pull` (for image that not found locally)
- `docker tag`
- `docker push`
- rewrite `/etc/docker/daemonjson`
- `systemctl restart docker`

## Prerequiste

If you want to use it on localhost, make sure you have your local repository installed.

This script uses `jq` to parse json

## Available options

- -p port, default: 5000
- -s server, default: localhost
- -t tag, default will use the given image name
- -h help, display help

## Usage

Normal usage
```bash
dockerx-push mysql:8.0
```

This will push to example.org:9900
```bash
dockerx-push -p 9900 -s example.org  mysql:8.0
```

This will retag `mysql:8.0` into `my-local-mysql:production`
```bash
dockerx-push -t my-local-mysql:production-version mysql:8.0
```
