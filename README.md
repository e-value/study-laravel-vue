# study-laravel-vue

## 概要

このプロジェクトは、Laravel（Sail）と Vite を利用した開発環境です。  
`localhost`でアプリケーション、`phpmyadmin`でデータベース管理画面を表示できます。

---

## セットアップ手順

### 1. リポジトリのクローン

```bash
git clone https://github.com/e-value/study-laravel-vue.git
cd study-laravel-vue
```

### 2. 環境変数ファイルの作成

```bash
cp .env.example .env
```

### 3. .env ファイルの設定

`.env`ファイルを以下の内容に設定してください：

```env
APP_NAME=Laravel
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost

LOG_CHANNEL=stack
LOG_DEPRECATIONS_CHANNEL=null
LOG_LEVEL=debug

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=study-laravel-vue
DB_USERNAME=laravel_user
DB_PASSWORD=password

BROADCAST_DRIVER=log
CACHE_DRIVER=file
FILESYSTEM_DISK=local
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120

MEMCACHED_HOST=memcached

REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_MAILER=smtp
MAIL_HOST=mailpit
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS="hello@example.com"
MAIL_FROM_NAME="${APP_NAME}"

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=
AWS_USE_PATH_STYLE_ENDPOINT=false

PUSHER_APP_ID=
PUSHER_APP_KEY=
PUSHER_APP_SECRET=
PUSHER_HOST=
PUSHER_PORT=443
PUSHER_SCHEME=https
PUSHER_APP_CLUSTER=mt1

VITE_APP_NAME="${APP_NAME}"
VITE_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
VITE_PUSHER_HOST="${PUSHER_HOST}"
VITE_PUSHER_PORT="${PUSHER_PORT}"
VITE_PUSHER_SCHEME="${PUSHER_SCHEME}"
VITE_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"
```

**※ キャッシュをクリア：**

```bash
sail artisan cache:clear && sail artisan config:cache
```

### 4. Composer インストール & Sail セットアップ

```bash
composer install
```

### 5. コンテナの起動（Sail）

```bash
sail up -d --build
```

### 6. アプリケーションキーの生成

```bash
sail artisan key:generate
```

### 7. マイグレーションの実行

```bash
sail artisan migrate
```

### 8. フロントエンド開発サーバー（Vite）の起動

```bash
sail npm install
sail npm run dev
```

---

## ブラウザでのアクセス

-   アプリケーション:  
    [http://localhost](http://localhost)

-   phpMyAdmin:  
    [http://localhost:8080](http://localhost:8080)

---

## その他のコマンド

-   コンテナの停止

```bash
sail down
```

-   テストの実行

```bash
sail artisan test
```

---

## 注意事項

-   `sail`コマンドはエイリアスが設定されている前提です。
-   コマンドは全てプロジェクトルートで実行してください。
-   `.env`の内容やポート番号は必要に応じて調整してください。

---
