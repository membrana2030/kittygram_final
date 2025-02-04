![GitHub Workflow Status](https://github.com/membrana2030/kittygram_final/actions/workflows/main.yml/badge.svg)

# Kittygram – платформа для любителей котиков

**Kittygram** – это веб-приложение, где пользователи могут выкладывать фотографии своих котиков, добавлять их имя, год рождения, цвет шерсти, а также просматривать котиков других пользователей.

## Функциональность проекта

-  Публикация фото котиков
-  Указание имени, года рождения и цвета котика
-  Просмотр и лайки котиков других пользователей
-  Админка для управления контентом
-  Авторизация и регистрация пользователей

---

## 🛠 Стек технологий

- **Backend:** Python 3, Django REST Framework, PostgreSQL
- **Frontend:** NodeJS
- **DevOps:** Docker, Docker Compose, GitHub Actions, Nginx
- **CI/CD:** Автоматическое тестирование и деплой через GitHub Actions
- **Хостинг:** Сервер на Ubuntu + Docker

---

##  Установка и запуск

### 1 Клонирование репозитория:

bash
git clone https://github.com/membrana2030/kittygram_final.git
cd kittygram_final

### 2️ Настройка .env файла:
Создайте файл .env в корне проекта и заполните его на основе .env.example:

POSTGRES_DB=kittygram
POSTGRES_USER=your_user
POSTGRES_PASSWORD=your_password
DB_HOST=db
DB_PORT=5432
DJANGO_SECRET_KEY=your_secret_key

### 3️ Запуск контейнеров:
docker-compose up -d --build
- Backend будет доступен на http://localhost:8000
- Frontend – http://localhost
- PostgreSQL – в контейнере db
- Nginx – http://localhost

### 4️ Применение миграций и сборка статики:
docker-compose exec backend python manage.py migrate
docker-compose exec backend python manage.py collectstatic

### Автоматический деплой (CI/CD)
Проект настроен на автоматический деплой с помощью GitHub Actions:

При пуше в main запускаются тесты.
Если тесты пройдены, Docker-образы отправляются в Docker Hub.
Обновляется сервер и автоматически перезапускаются контейнеры.
В Telegram отправляется уведомление о деплое.

# Как убедиться, что деплой сработал?

1. Перейти по https://kittygrammembrana.hopto.org/
2. Проверить, что сайт работает корректно.

### Автор
Разработчик: Lev Fridman (https://github.com/membrana2030)
Проект создан в рамках учебного задания.
