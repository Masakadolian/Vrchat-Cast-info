
# フルスタックDocker環境 (Django + React + PostgreSQL + Nginx)

## 概要

このプロジェクトは以下をまとめたWebアプリの基本的な環境です：

- **Django**: サーバーサイド（バックエンド）
- **React (Next.js)**: クライアントサイド（フロントエンド）
- **PostgreSQL**: データベース
- **Nginx**: リバースプロキシサーバー

すべてを **Docker** を使って動かします。

---

## 必要なもの

1. **Docker** と **Docker Compose** をインストール  
   - Dockerバージョン: `27.3`
   - Docker Composeバージョン: `2.29.7`
2. **Git** のインストール
3. **コマンドを打てる環境** (例: ターミナル、コマンドプロンプト)

---

## プロジェクトの起動方法

### 1. リポジトリをダウンロード（Gitで取得）

まず、このプロジェクトを自分のパソコンにコピーします。

```bash
# 1. Gitを使ってプロジェクトをコピー
git clone https://github.com/<your-repo-name>/docker-fullstack.git

# 2. プロジェクトのフォルダに移動
cd docker-fullstack
```

もしGitが使えない場合は、[Gitの公式サイト](https://git-scm.com/)でインストールしてから再試行してください。

---

### 2. 環境ファイルの作成

`.env` ファイルを作成し、以下の内容を記入してください。

```env
POSTGRES_DB=your_database_name
POSTGRES_USER=your_database_user
POSTGRES_PASSWORD=your_database_password
```

- `your_database_name`: データベース名を指定 (例: `mydb`)
- `your_database_user`: データベースユーザーを指定 (例: `myuser`)
- `your_database_password`: パスワードを指定 (例: `mypassword`)

---

### 3. Dockerを使ってサービスを起動

以下のコマンドを実行して、すべてのサービスを起動します。

```bash
docker-compose up --build
```

初回は少し時間がかかる場合がありますが、辛抱強く待ちましょう！

---

### 4. サービスの確認

- **Reactフロントエンド**: [http://localhost](http://localhost)  
  → ここでアプリの画面が表示されます。

- **DjangoバックエンドAPI**: [http://localhost/api/](http://localhost/api/)  
  → APIが動作しているか確認できます。

---

## 各コンポーネントの簡単な説明

### **Nginx**

Nginxは、以下の役割を果たします：

- `/` は React (Next.js) にルーティング  
- `/api/` は Django にルーティング

**初心者ポイント**: Nginxはアプリへの「玄関」のような役割を持っています。

---

### **Django**

Djangoは「バックエンド」の部分で、データベースと連携してデータを管理します。  
主にAPIを作成するために使用します。

```bash
# Django管理画面の作成例 (初回のみ)
docker exec -it django_backend python3 manage.py createsuperuser
```

作成した管理者アカウントで `/admin` にアクセスできます。

---

### **React (Next.js)**

Reactは「フロントエンド」を作るためのフレームワークです。画面に表示される要素を管理します。

**初期状態**: このプロジェクトには簡単なテンプレートが含まれています。 `frontend/src` を編集するとカスタマイズできます。

---

### **PostgreSQL**

PostgreSQLはアプリケーションのデータを保存するデータベースです。このプロジェクトでは `db/data` にデータが保存されます。

---

## よくある質問

### **Q: Dockerが動かない場合はどうすればいい？**

1. Dockerがインストールされているか確認します。
   ```bash
   docker --version
   docker-compose --version
   ```
2. サービスが正しく動いていない場合は以下を試してください。
   ```bash
   docker-compose down
   docker-compose up --build
   ```

---

## Gitに上げる方法

### 1. 初めての設定

Gitを初めて使う場合、以下を設定してください。

```bash
git config --global user.name "あなたの名前"
git config --global user.email "あなたのメールアドレス"
```

### 2. プロジェクトをGitHubにアップロード

```bash
# 1. 変更されたファイルをステージング
git add .

# 2. 変更を記録
git commit -m "初回のアップロード"

# 3. GitHubリポジトリにプッシュ
git push origin main
```

---

## まとめ

このプロジェクトは、フロントエンド、バックエンド、データベースをすべてDockerで管理できる便利な環境です。わからないことがあれば、一歩ずつ進んでいきましょう！ 🚀
