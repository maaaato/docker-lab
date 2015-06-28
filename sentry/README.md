# Sentry Dockerfiles

## Description

Sentry with Docker

## Setup

MySQL,Redis,Ningx,Sentry

```
docker run -d --name mysql-docker MYSQL_IMAGE
```
Run Command 'CREATE DATABASE sentry;'

```
docker run -d --name redis-docker REDIS_IMAGE
docker run -d --name sentry-docker --link mysql-docker:mysql-docker --link redis-docker:redis-docker SENTRY_IMAGE
docker run -d --name nginx --link sentry-docker:sentry-docker -p 80:80 NGINX_IMAGE
```

sentry start.CUI Message Answer.

SuperUser Create.

# Author

[Masayuki Nakano](https://github.com/maaaato)
