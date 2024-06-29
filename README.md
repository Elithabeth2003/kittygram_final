# Kittygram_final

[![Build Status](https://github.com/Elithabeth2003/kittygram_final/actions/workflows/docker-image.yml/badge.svg)](https://github.com/Elithabeth2003/kittygram_final/actions)

## Описание

Kittygram - это социальная сеть, специально созданная для хозяев и любителей милых кошечек. Здесь можно делиться фотографиями своих питомцев, обмениваться опытом и заводить новых друзей с общими кошачьими интересами. Пользователи могут создавать профили своих котов, загружать фотографии, описывать их особенности и достижения.

## Функциональность

- Регистрация и авторизация пользователей
- Создание и редактирование профилей питомцев
- Загрузка и просмотр фотографий котов
- Поиск и подписка на других пользователей
- Ведение блога о жизни своих питомцев

## Технологический стек

- Python
- Django
- Django REST Framework
- Gunicorn
- Nginx
- Docker Compose
- GitHub Actions
- PostgreSQL (SQLite)

## Как развернуть проект

### Шаг 1: Клонируйте репозиторий

```
git clone git@github.com:Elithabeth2003/kittygram_final.git
```

### Шаг 2: Создайте файл .env

```
cd kittygram_final
touch .env
```

### Шаг 3: Заполните переменные окружения в .env файле

```
POSTGRES_DB=<БазаДанных>
POSTGRES_USER=<имя пользователя>
POSTGRES_PASSWORD=<пароль>
DB_NAME=<имя БазыДанных>
DB_HOST=db
DB_PORT=5432
SECRET_KEY=<ключ Django>
DEBUG= <True/False>
USE_SQLITE= <True/False>
ALLOWED_HOSTS=<разрешенные хосты>
TIME_ZONE=<Время>
```

### Шаг 4: Установите Docker и Docker Compose

```
sudo apt update
sudo apt-get install docker-compose-plugin
```

### Шаг 5: Запустите Docker Compose

```
sudo docker-compose -f docker-compose.yml up -d
```

### Шаг 6: Выполните миграции и соберите статику

```
sudo docker-compose exec backend python manage.py migrate
sudo docker-compose exec backend python manage.py collectstatic --noinput
```

## Автодеплой с помощью GitHub Actions
Для настройки автодеплоя добавьте следующие переменные в Secrets вашего репозитория:

- DOCKER_PASSWORD - пароль от Docker Hub
- DOCKER_USERNAME - имя пользователя Docker Hub
- HOST - IP сервера
- SSH_KEY - ключ SSH для доступа к удаленному серверу
- SSH_PASSPHRASE - пароль SSH
- TELEGRAM_TO - ID пользователя TELEGRAM
- TELEGRAM_TOKEN - TELEGRAM токен
- USER - имя пользователя сервера

## Автор

[Elithabeth2003](https://github.com/Elithabeth2003)
