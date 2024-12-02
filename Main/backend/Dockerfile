# ベースイメージ
FROM python:3.11-slim-bullseye

# システムパッケージのインストール
RUN apt-get update && apt-get install -y --no-install-recommends \
    gcc libpq-dev && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# 作業ディレクトリ設定
WORKDIR /app

# 必要パッケージのコピーとインストール
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# ソースコードのコピー
COPY src/ /app/

# Djangoアプリのエントリポイント
CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]

