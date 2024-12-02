# ベースイメージ
FROM node:20-alpine

# 作業ディレクトリ設定
WORKDIR /app

# 必要パッケージのコピーとインストール
COPY src/package.json src/package-lock.json ./
RUN npm install

# ソースコードのコピー
COPY src/ /app/

# Next.js アプリのエントリポイント
CMD ["npm", "run", "dev"]
