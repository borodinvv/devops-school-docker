# Homework 1. Docker

Задача: развернуть приложение "2048".

## Клонируем репозиторий с приложением

```bash
$ git clone git@github.com:gabrielecirulli/2048.git
```

## Создаем Dockerfile

```bash
FROM nginx:alpine

MAINTAINER Vladislav Borodin <vladislav_borodin@epam.com>

COPY $PWD/2048 /usr/share/nginx/html

ENTRYPOINT ["nginx", "-g", "daemon off;"]
```
 
## Собираем образ и запускаем контейнер 

```bash
$ docker build -t 2048-vvb .
$ docker run -d --name 2048 -p 8181:80 2048-vvb
```
## Скриншот
![alt text](https://github.com/borodinvv/devops-school-docker/tree/master/1/2048.png)