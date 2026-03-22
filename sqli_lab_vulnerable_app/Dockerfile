FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

# Crear carpeta para la base de datos
RUN mkdir -p db

EXPOSE 5000

CMD ["python", "app.py"]
