# 🐱 Kittygram

**Kittygram** — это веб-приложение для публикации и просмотра фотографий котиков.
Проект состоит из backend (Django REST), frontend (React) и полностью контейнеризирован с помощью Docker.

---

## 🚀 Стек технологий

### Backend

* Python 3.9
* Django
* Django REST Framework
* PostgreSQL
* Gunicorn

### Frontend

* React
* Node.js
* HTML / CSS / JS

### Infrastructure

* Docker
* Docker Compose
* Nginx

### CI/CD

* GitHub Actions
* Ruff (lint)
* Docker Hub
* Telegram notifications

---

## 📦 Запуск проекта через Docker

### 1. Клонировать репозиторий

```bash
git clone https://github.com/StaPi420/kittygram_final.git
cd kittygram_final
```

---

### 2. Создать `.env`

```env
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password

DB_HOST=db
DB_PORT=5432

SECRET_KEY=your-secret-key
DEBUG=False
ALLOWED_HOSTS=*
```

---

### 3. Запуск проекта

```bash
docker-compose up --build
```

---

## 🌐 Доступ к приложению

После запуска:

* Frontend → [http://localhost/](http://localhost/)
* API → [http://localhost/api/](http://localhost/api/)
* Admin → [http://localhost/admin/](http://localhost/admin/)

---

## 🛠️ Миграции и статика

После первого запуска:

```bash
docker-compose exec backend python manage.py migrate
docker-compose exec backend python manage.py collectstatic
docker-compose exec backend python manage.py createsuperuser
```

---

## 🐘 Настройка PostgreSQL

Проект автоматически подключается к базе через Docker Compose.

Используется:

* сервис `db`
* переменные из `.env`

---

## 🐳 Архитектура проекта

```
frontend  → React
backend   → Django REST API
db        → PostgreSQL
gateway   → Nginx
```

---

## 🔄 CI/CD (GitHub Actions)

При push в `main` происходит:

1. Проверка кода (ruff)
2. Запуск тестов backend и frontend
3. Сборка Docker образов:

   * kittygram_backend
   * kittygram_frontend
   * kittygram_gateway
4. Отправка в Docker Hub
5. Уведомление в Telegram

---

## 🐋 Docker Hub образы

```text
username/kittygram_backend
username/kittygram_frontend
username/kittygram_gateway
```

---

## 📁 Структура проекта

```
backend/
frontend/
nginx/
docker-compose.yml
.github/workflows/
```

---

## 📸 Возможности проекта

* Регистрация пользователей
* Добавление котиков
* Загрузка изображений
* Просмотр профилей
* REST API

---

## 🚀 Автор

Проект выполнен в рамках учебного задания по контейнеризации и CI/CD.

---

## 📌 Примечание

Проект полностью работает в Docker и не требует локальной установки зависимостей.

---
