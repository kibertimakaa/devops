# Как использовать Docker

## Основные команды Docker
- docker --version — проверить версию Docker.
- docker pull образ — загрузить образ из Docker Hub.
- docker images — показать список локальных образов.
- docker run параметры образ — запустить контейнер из образа.
- docker ps — показать запущенные контейнеры.
- docker ps -a — показать все контейнеры (включая остановленные).
- docker stop ID — остановить контейнер.
- docker rm ID — удалить контейнер.
- docker rmi образ — удалить образ.

## Типичный рабочий процесс

1. Установить Docker и проверить работу:

```
sudo apt update && sudo apt install docker.io
sudo docker run hello-world
```

2. Загрузить официальный образ:

```
docker pull nginx:latest
```

3. Запустить контейнер с портами:

```
docker run -d -p 8080:80 --name my-nginx nginx
```

4. Просмотреть логи контейнера:

```
docker logs my-nginx
```

5. Остановить и удалить контейнер:

```
docker stop my-nginx
docker rm my-nginx
```

6. Создать свой Dockerfile и собрать образ:

```
docker build -t myapp .
```

TODO: Implement how to work with docker compose
