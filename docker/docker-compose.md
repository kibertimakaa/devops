# Как использовать Docker Compose

## Основные команды Docker Compose
- `docker-compose --version` — проверить версию Docker Compose.
- `docker-compose up` — запуск всех сервисов, описанных в docker-compose.yml.
- `docker-compose up -d` — запуск сервисов в фоновом режиме (detached).
- `docker-compose down` — остановка и удаление контейнеров, сетей и томов, созданных Compose.
- `docker-compose ps` — показать запущенные сервисы.
- `docker-compose logs` — показать логи всех сервисов.
- `docker-compose logs сервис` — показать логи конкретного сервиса.
- `docker-compose stop` — остановить запущенные сервисы.
- `docker-compose restart` — перезапустить сервисы.
- `docker-compose build` — собрать образы из Dockerfile перед запуском.

## Типичный рабочий процесс

1. Создать файл `docker-compose.yml` в корне проекта:

```
version: '3.8'

services:
web:
image: nginx:latest
ports:
- "8080:80"

app:
build: .
ports:
- "5000:5000"
volumes:
- .:/app
depends_on:
- db

db:
image: postgres:13
environment:
POSTGRES_USER: user
POSTGRES_PASSWORD: password
POSTGRES_DB: mydb
```


2. Запустить сервисы в фоновом режиме:

```
docker-compose up -d
```

3. Проверить, что контейнеры запущены:

```
docker-compose ps
```

4. Просмотреть логи определённого сервиса:

```
docker-compose logs app
```

5. Остановить и удалить сервисы:

```
docker-compose down
```

6. Пересобрать образы при необходимости:

```
docker-compose build
```
