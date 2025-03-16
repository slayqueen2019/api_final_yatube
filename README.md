# API для проекта Yatube

## 1. [Описание](#1)

## 2. [Инструкции для запуска](#2)

## 3. [Доступные эндпоинты](#3)

## 4. [Примеры запросов](#4)

## 5. [Технические детали](#5)

## 6. [Об авторе](#6)

---

## 1. Описание

Проект API для социальной сети Yatube.  
Позволяет создавать, просматривать, рекдактировать и удалять свои посты, а также знакомиться с постами других пользователей и подписываться на их профили, используя API-запросы.

---

## 2. Инструкции для запуска

Перед запуском необходимо склонировать проект:

```bash
HTTPS: git clone https://github.com/DIABLik666/api_final_yatube.git
SSH: git clone git@github.com:DIABLik666/api_final_yatube.git
```

Cоздать и активировать виртуальное окружение:

```bash
python -m venv venv
```

```bash
Linux: source venv/bin/activate
Windows: source venv/Scripts/activate
```

И установить зависимости из файла requirements.txt:

```bash
python3 -m pip install --upgrade pip
```

```bash
pip install -r requirements.txt
```

Выполнить миграции:

```bash
python3 manage.py migrate
```

Запустить проект:

```bash
python3 manage.py runserver
```

Теперь работоспособность проекта можно проверить по адресу [http://localhost/admin/](http://localhost/admin/)

---

## 3. Доступные эндпоинты

Посты:

```
"/api/v1/posts/" (Параметры для фильтрации "?limit=0&offset=0"),
"/api/v1/posts/{id}/"
```

Группы:

```
"/api/v1/groups/",
"/api/v1/groups/{id}/"
```

Комментарии:

```
"/api/v1/posts/{id}/comments/",
"/api/v1/posts/{id}/comments/{id}/"
```

Подписки (Только для авторизованных пользователей):

```
"/api/v1/follow/" (Параметр для поиска "?search=''")
```

Получение токена для доступа к API (Для зарегистрированных пользователей):

```
"/api/v1/auth/jwt/create/"
```

---

## 4. Примеры запросов

Получение списка всех постов:

```
Method: GET
Endpoint: "/api/v1/posts/"
```

Публикация поста:

```
Method: POST
Endpoint: "/api/v1/posts/"
Payload:
{
    "text": "string",
    "image": "string",
    "group": 0
}
```

Аутенфикация и получение JWT-токена:

```
Method: POST
Endpoint: "/api/v1/auth/jwt/create/"
Payload:
{
    "username": "string",
    "password": "string"
}
```

---

## 5. Технические детали

Стек технологий: Python 3.10, Django, Django Rest, simple JWT.

---

## 6. Об авторе

Гончарук Анастасия Александровна
ML-инженер
Россия, г. Москва  
E-mail: nastgoncharuk@yandex.ru  
Telegram: @GoncharukNastya
