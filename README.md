# Vrchat-Cast-info
VrchatCast.infoの開発用の場所です。タスクの管理もここで行います
---

# フルスタックプロジェクト: Django + React + PostgreSQL + Nginx

こんにちは！  
これは **Django** (バックエンド)、**React** (フロントエンド)、**PostgreSQL** (データベース)、**Nginx** (サーバー) を使ったWebアプリプロジェクトです。すべてを **Docker** で管理します！

---

## プロジェクトのフォルダ構成

プロジェクトの中身はこんな感じになっています：

```
Main/
├── backend/              # Django (サーバーのコード)
├── frontend/             # React (画面のコード)
├── nginx/                # Nginx (Webサーバーの設定)
├── db/                   # PostgreSQL (データベース)
├── docker-compose.yml    # Docker全体の設定
├── .env                  # 環境変数 (自分で作成)
└── README.md             # この説明書！
```

---

## 始め方（最初だけやること）

### 1. リポジトリをコピー
GitHubからプロジェクトをコピーしてパソコンに持ってきます。

```bash
git clone https://github.com/<your-repo-name>/docker-fullstack.git
cd Main
```

---

### 2. 環境変数ファイルの準備

1. プロジェクトのフォルダに移動。
2. 新しく `.env` という名前のファイルを作る。
3. 以下の内容をコピペして保存。

```env
POSTGRES_DB=your_database_name
POSTGRES_USER=your_database_user
POSTGRES_PASSWORD=your_database_password
```

> "your_" 以降は自分で好きな名前やパスワードに変えてね！

---

### 3. Dockerでプロジェクトを起動

```bash
docker-compose up --build
```

これでプロジェクトが動き始めます！  

**確認する場所：**
- [http://localhost](http://localhost): フロントエンド (画面)
- [http://localhost/api/](http://localhost/api/): バックエンド (API)

---

## GitHubプロジェクトの使い方

### 1. タスクの作り方

1. GitHubのリポジトリページに行く。
2. 上のメニューから **Projects** をクリック。
3. **New Project** ボタンを押して、新しいタスクボードを作る。
4. カラムを作る（例: `To Do`、`In Progress`、`Done`）。
5. タスクを作るときは **+ Add a card** をクリックして、やることを書く。

---

### 2. タスクの進め方

- 自分のタスクを選んでドラッグ＆ドロップで進行状況を更新！
  - **To Do**: やること
  - **In Progress**: 進行中
  - **Done**: 完了

---

## プルリクエストの作り方

チームで一緒に作業するときに便利な方法です。

### 手順

1. **新しいブランチを作る**:
   ```bash
   git checkout -b feature/branch-name
   ```

2. **変更をステージングする**:
   ```bash
   git add .
   ```

3. **コミットメッセージを追加**:
   ```bash
   git commit -m "何を変えたか分かる説明"
   ```

4. **リポジトリにプッシュする**:
   ```bash
   git push origin feature/branch-name
   ```

5. GitHubに行き、**Pull Request (PR)** を作成する。

6. レビューが完了したらマージ（統合）！

---

## Dockerの基本操作

### サービスを終了する

```bash
docker-compose down
```

### コンテナをリセットする（全部やり直し）

```bash
docker-compose down -v
```

---

## 困ったときは？

- **Dockerが動かない**  
  → コマンド `docker ps` でサービスが動いているか確認。

- **ReactやDjangoでエラーが出る**  
  → コードを修正後に `docker-compose up --build` を実行。

---

## おまけ: 小さなヒント

- **Djangoの管理画面を見る**:
  ```bash
  docker exec -it django_backend python manage.py createsuperuser
  ```
  → [http://localhost/admin](http://localhost/admin) にアクセス。

- **Reactのコードを編集する**:
  フォルダ `frontend/src` の中を見てみよう！

---

これでおしまい！分からないことがあったら、質問するのを忘れないでね。🎉

