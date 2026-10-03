# YaNews

Учебный проект Django с новостями и комментариями. Главная страница показывает последние новости; автор может редактировать и удалять свои комментарии. После миграций можно загрузить демонстрационные записи из `news/fixtures/news.json`.

Нужен Python 3.9 и SQLite. Настройки из `.env.example` передаются как переменные окружения; `.env` автоматически не загружается.

```powershell
py -3.9 -m venv .venv
.venv\Scripts\python -m pip install -r requirements.txt
.venv\Scripts\python manage.py migrate
.venv\Scripts\python manage.py loaddata news.json
.venv\Scripts\python manage.py runserver
```

Тесты используют отдельную временную базу Django:

```powershell
.venv\Scripts\python -m pytest -q
```

Для `DJANGO_DEBUG=0` задайте `DJANGO_SECRET_KEY` и `DJANGO_ALLOWED_HOSTS`.
