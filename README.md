# Kittygram - блог для размещения фотографий котиков

## Описание проекта

Kittygram позволяет пользователям делиться фотографиями своих питомцев-кошек. Зарегистрированные пользователи могут создавать посты с фото, просматривать, редактировать и удалять их.

## Возможности

- Регистрация и аутентификация пользователей
- Создание постов с фотографиями кошек
- Просмотр ленты постов от подписок
- Поиск постов по тегам
- Редактирование и удаление собственных постов 

## Используемые технологии

- Python 3.9
- Django 3.2  
- Gunicorn
- React
- PostgreSQL 
- Docker и Docker Compose
- Nginx

## Установка

### 1. Настройка .env файла

Скопируйте `.env.example` в `.env` и укажите необходимые параметры:

```  
# Настройки Postgres
POSTGRES_DB=kittygram
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password

# Настройки Django
DB_NAME=kittygram
DB_HOST=db
DB_PORT=5432
SECRET_KEY=mysecretkey
DEBUG=False
ALLOWED_HOSTS=127.0.0.1 localhost
```

### 2. Запуск Docker

```
docker-compose up -d 
```

Приложение будет доступно по адресу http://127.0.0.1:9000

## Команды
- `docker-compose up -d` - Запуск контейнеров

- `sudo docker compose -f docker-compose.production.yml down` - Остановка контейнеров
- `sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate` - Миграции Django
- `sudo docker compose -f docker-compose.production.yml exec backend python manage.py createsuperuser` - Создание админа
- `sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic` - Сборка статики
- `sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/` - Копирование статики в volume

## Автор

Леонид Косков [@leonid-koskov](https://github.com/coskoff1988)