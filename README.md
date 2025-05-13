# Проект Киттиграм - это социальная сеть для любителей котиков.
Kittygram - социальная сеть, для любителей кошечек

## Как развернуть
1. Скачайте docker-compose.yml из репозитория https://github.com/ItFromMurmansk/kittygram_final/docker-compose.yml
2. Создайте файл .env
```
touch .env
```
3. Создайте файл с переменными окружения
```
POSTGRES_DB=<БазаДанных>
POSTGRES_USER=<имя пользователя>
POSTGRES_PASSWORD=<пароль>
POSTGRES_DB_NAME=<имя БазыДанных>
POSTGRES_DB_HOST=db
POSTGRES_DB_PORT=5432
```

4. Запустите Dockercompose
```
sudo docker compose -f docker-compose.yml pull
sudo docker compose -f docker-compose.yml down
sudo docker compose -f docker-compose.yml up -d
```
5. Сделайте миграции и соберите статику
```
sudo docker compose -f docker-compose.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.yml exec backend cp -r /app/collected_static/. /backend_static/static/ 
```

## Автодеплой на Git Hub Action
Добавьте перменные в Secrets
```
DOCKER_PASSWORD - пароль от Docker Hub
DOCKER_USERNAME - имя пользователя Docker Hub
HOST - ip сервера
SSH_KEY - ключ ssh для доступа к удаленному серверу
SSH_PASSPHRASE - пароль ssh
```

## Технологии

2. Backend:
Django
DRF
Gunicorn

4. Сервер:
nginx

5. Деплой
Docker
Docker compose

## Автор: Dmitry Tronin https://github.com/ItFromMurmansk

<<<<<<< HEAD
[![Main Kittygram workflow](https://github.com/ItFromMurmansk/kittygram_final/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/ItFromMurmansk/kittygram_final/actions/workflows/main.yml)
=======
[![Main Kittygram workflow](https://github.com/ItFromMurmansk/kittygram_final/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/ItFromMurmansk/kittygram_final/actions/workflows/main.yml)
>>>>>>> 8f4b661cc3c057c43070f8454bb9fcebe31f5c6c
