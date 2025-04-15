FROM python:3.11-slim

RUN useradd -m simpleuser

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .

USER simpleuser

EXPOSE 5000

CMD ["python", "app.py"]
