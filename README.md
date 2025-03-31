# API для Yatube

API для социальной сети Yatube. Позволяет пользователям создавать посты, комментировать их, подписываться на авторов и управлять подписками через программный интерфейс.

## Возможности API

- Создание, редактирование, удаление и просмотр постов
- Комментирование постов
- Подписка и отписка от авторов
- Просмотр и создание групп
- Фильтрация и поиск по постам
- JWT-аутентификация

## Технологии

- Python 3.7+
- Django 3.2.16
- Django REST framework 3.12.4
- JWT для аутентификации

## Как запустить проект

1. Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/kanzlerath/api_final_yatube
cd api_final_yatube
```

2. Создать и активировать виртуальное окружение:
```
python3 -m venv venv
source venv/bin/activate
```

3. Установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```

4. Выполнить миграции:
```
python3 manage.py migrate
```

5. Запустить проект:
```
python3 manage.py runserver
```

## Примеры использования API

### Получение токена
```bash
POST /api/v1/jwt/create/
{
    "username": "string",
    "password": "string"
}
```

### Создание публикации
```bash
POST /api/v1/posts/
{
    "text": "string",
    "image": "string",
    "group": 0
}
```

### Получение публикаций
```bash
GET /api/v1/posts/
```

### Работа с комментариями
```bash
# Получение комментариев
GET /api/v1/posts/{post_id}/comments/

# Создание комментария
POST /api/v1/posts/{post_id}/comments/
{
    "text": "string"
}
```

### Подписки
```bash
# Получение подписок
GET /api/v1/follow/

# Создание подписки
POST /api/v1/follow/
{
    "following": "string"
}
```

## Документация API

Полная документация доступна по адресу `http://localhost:8000/redoc/` после запуска проекта.
