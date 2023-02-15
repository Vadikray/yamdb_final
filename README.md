# API_YAMDB ![Yamdb Status](https://github.com/vadikray/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?branch=master&event=push)
***
## Документация проекта: http://84.201.136.205/redoc/
## Описание проекта
Проект Yamdb собирает отзывы пользователей на произведения.
Работы разделены на категории: «Книги», «Фильмы», «Музыка».
Сами произведения в Yamdb не хранятся; здесь нельзя смотреть кино или слушать музыку.
В каждой категории есть работы: книги, фильмы или музыка.
***
## инструкция
Клонируйте репозиторий
```
git@github.com:Vadikray/yamdb_final.git
```
Перейдите в infra
```
cd infra
```
Запуск docker-compose
```
docker-compose up -d --build
```
Выполните по очереди команды(Применение миграций, создания суперпользователя и собрать статику)
```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input 
```
Команда для заполнения базы(в этом проекте ее нет)
```
docker-compose exec web python manage.py loaddata fixtures.json
```


Шаблон наполнения .env
```
DB_ENGINE=django.db.backends.postgresql 
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
DJANGO_KEY=&25k@3hm-s1d)5c-zu3_45ycih+!5&717(b$*d)zg341xo#p$e
```
# Автор: Конюшков В.А.