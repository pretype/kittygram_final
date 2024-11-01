# Проект 11-го спринта Kittygram-Final
###### @Яндекс Практикум
***

## Workflow status badge (Бейдж сборки)
[![Main Kittygram workflow](https://github.com/pretype/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/pretype/kittygram_final/actions/workflows/main.yml)

***

## Использованные технологии

Python
Django
Django REST framework
Nginx
Docker
Docker Hub
Git
GitHub

Иные использованные технологии и их версии, указаны в файле "requirements.txt".

***

## Описание

Проект Kittygram, создан любителями котиков для любителей котиков!
После регистрации на сайте проекта, пользователь может просматривать карточки котиков, любуясь их фотографиями и удивляясь их достижениям.
Также, пользователь может добавить карточку своего котика, указав его имя, год рождения, цвет, достижения и прикрепив фотографию.

***

## Локальные установка и запуск проекта

<details>
  <summary><b<strong>Локальная установка и запуск проекта</strong></b></summary>

1. Убедитесь, что у Вас развернуты виртуальная машина и Docker

2. Клонируйте проект kittygram_final с GitHub:
  ```bash
  git clone https://github.com/pretype/kittygram_final
  ```

3. Перейдите в локальную директорию проекта kittygram_final

4. В корневой директории проекта, создайте файл ".env", внесите в него переменные, указанные ниже, и их значения:
POSTGRES_USER
POSTGRES_PASSWORD
POSTGRES_DB
DB_HOST
DB_PORT
SECRET_KEY

5. Из корневой папки проекта запустите Docker-compose

  ```bash
  docker compose up
  ```

6. В другом терминале, из корневой папки проекта, выполните миграции, сбор и копировании статики

  ```bash
  docker compose exec backend python manage.py migrate
  docker compose exec backend python manage.py collectstatic
  docker compose exec backend cp -r /app/collected_static/. /backend_static/static/
  ```

Проект будет доступен по веб-адресу:
http://localhost:9000/

</details>

***

## Примеры
### Пример API POST-запроса от авторизованного пользователя
Добавление котика, POST /api/cats/

{
    "color": "#000000",
    "achievements": [],
    "name": "Тест",
    "birth_year": "2024"
}

### Пример API ответа
Просмотр котика, GET /api/cats/

{
    "id": 17,
    "name": "Тест",
    "color": "black",
    "birth_year": 2024,
    "achievements": [],
    "owner": 1,
    "age": 0,
    "image": null,
    "image_url": null
}
