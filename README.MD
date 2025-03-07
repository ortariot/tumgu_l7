# Вебинар 7. Тестирование WEB-приложения

- не работало потому что миграции не были применены к бд. Проверяйте!!
- обратите внимание на /update_filds_role/ 

## requirements:
```
asyncpg==0.30.0
celery==5.4.0
fastapi==0.115.8
httpx==0.28.1
passlib==1.7.4
psycopg2-binary==2.9.10
pydantic==2.10.6
PyJWT==2.10.1
redis==5.2.1
requests==2.32.3
SQLAlchemy==2.0.38
pydantic_settings==2.8.1
pytest==8.3.5
pytest-asyncio==0.25.3
```

## to start:

- docker run --name redis -d -p 6379:6379 redis
- docker run --name pg_test -p 5432:5432 -e POSTGRES_PASSWORD=postgres -d postgres:latest 
- python -m venv env (создать вирутальное окружение)
- pip install -r requirements.txt
- souce env/bin/activate (linux) env/scripts/activate (windows)
- python db/models/models.py (создать таблицы в бд)
- python main.py (запуск)


## celery start:

- celery -A tasker.task worker --loglevel=info


## tests start:

- pytest tests/src/ 