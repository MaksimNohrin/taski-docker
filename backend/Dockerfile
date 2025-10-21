# Создать образ на основе базового слоя,
# который содержит файлы ОС и интерпретатор Python 3.12.
FROM python:3.12

WORKDIR /app
RUN pip install gunicorn==23.0.0

# Скопировать с локального компьютера файл зависимостей
# в текущую директорию (текущая директория — это /app).
COPY requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir
COPY . .

# При старте контейнера запустить сервер разработки.
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
