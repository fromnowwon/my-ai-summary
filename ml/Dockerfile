FROM python:3.10-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000"]FROM python:3.10-slim

WORKDIR /app

# 필수 시스템 패키지 설치 (transformers, torch 등 설치 오류 방지용)
RUN apt-get update && apt-get install -y \
    build-essential \
    git \
    curl \
 && rm -rf /var/lib/apt/lists/*

# Python 패키지 설치
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000"]