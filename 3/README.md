# Homework 3. Docker

Задача: развернуть сервис с двумя вебсерверами.

## Запускаем контейнер с local registry

```bash
$ docker run -d -p 5000:5000 --restart=always --name registry registry:2
```

## Создаем образ NGINX и добавляем в local registry

```bash
$ docker build -t nginx-web-server:latest -t nginx-web-server:1.0 -f Dockerfile.nginx .
$ docker image tag nginx-web-server:1.0 localhost:5000/nginx-web-server:1.0 
$ docker push localhost:5000/nginx-web-server:1.0
```
## Создаем образ APACHE и добавляем в local registry
```bash
$ docker build -t apache-web-server:latest -t apache-web-server:1.0 -f Dockerfile.apache .
$ docker image tag apache-web-server:1.0 localhost:5000/apache-web-server:1.0 
$ docker push localhost:5000/apache-web-server:1.0
```

## Запускаем сервис через Docker-compose
```bash
$ docker-compose up -d
```