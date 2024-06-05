# Використовуємо базовий образ Python
FROM python:3.12-slim

# Встановлюємо змінні середовища
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Встановлюємо робочу директорію
WORKDIR /code

# Копіюємо файли та встановлюємо залежності
COPY requirements.txt /code/
RUN pip install --upgrade pip
RUN pip install -r requirements.txt
COPY . /code/

# Збираємо статичні файли
RUN python manage.py collectstatic --noinput

# Встановлюємо Gunicorn
RUN pip install gunicorn

# Виконуємо міграції бази даних
RUN python manage.py migrate

# Вказуємо, на якому порті працює додаток
EXPOSE 8000

# Запускаємо Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "myproject.wsgi:application"]
