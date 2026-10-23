# Развёртывание backend (бесплатный тариф Render.com)

1. Зарегистрируйтесь на render.com (можно через GitHub).
2. Создайте отдельный ПРИВАТНЫЙ репозиторий (например cm-backend) и загрузите в него
   папку backend/ (server.js, lib/, package.json, .env.example).
3. Render → New → Web Service → выберите репозиторий.
4. Build Command: npm install
   Start Command: node server.js
5. В разделе Environment добавьте переменные из .env.example
   (PORT задаёт Render сам, не указывайте).
6. После деплоя скопируйте адрес вида https://cm-backend.onrender.com и вставьте
   его в apiBase в assets/js/config.js сайта.

## Ограничения бесплатного тарифа Render
Сервер «засыпает» без запросов ~15 минут (первый запрос после паузы — до 30 сек).
Для старта приемлемо; при росте продаж — платный тариф (~$7/мес).

## База данных
Используется SQLite (файл data.sqlite создаётся автоматически на сервере).
При росте — бесплатная PostgreSQL на Neon или Render, код запросов тот же.
