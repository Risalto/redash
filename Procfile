release: python manage.py database create_tables
web: gunicorn -b 0.0.0.0:$PORT -w4 redash.wsgi:app
worker: celery worker --app=redash.worker -c${REDASH_HEROKU_CELERY_WORKER_COUNT:-2} --beat -Q queries,celery,scheduled_queries

