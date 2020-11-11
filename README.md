# LAMPD環境
Linux * Apache * Mysql * PHP(Laravel) * Docker

## コンテナ立ち上げ
```
$ docker-compose build
```

## コンテナ起動
```
$ docker-compose up
```

### バックグラウンド起動
```
$ docker-compose up -d
```

## プロセス確認
```
$ docker ps
```

## コンテナ停止
```
$ docker-compose stop
```

## Laravelコンテナログイン
```
$ docker exec -it laravel bash
```

## clone時のみ
### 1. composerインストール
```
$ composer install
```
### 2. .envファイル修正
```
$ cp .env.example .env
```
DB_CONNECTION=mysql  
DB_HOST=mysql  
DB_PORT=3306  
DB_DATABASE=laravel_db  
DB_USERNAME=laravel_user  
DB_PASSWORD=password  
### 3. APP_KEYの生成
```
$ php artisan key:generate
```

## migrateの実行
```
$ docker exec -it laravel_app bash
$ cd laravelapp
$ php artisan migrate
```

## migrateファイル作成（テーブル名は複数系）
```
$ php artisan make:migration create_[table-name]s_table --create=[table-name]s
```

## Modelファイル作成（大文字開始かつ単数系）
```
$ php artisan make:model モデル名
```

## Controllerファイル作成（開始文字大文字）
```
$ php artisan make:controller コントローラー名sController
```

## Sassの導入
1. composer.jsonファイル追加
```
require-devに以下の内容を追加  
"panique/laravel-sass": "dev-master",
```

2. SCSSをCSSに変換する処理を追加
```
public/index.php 最終行に以下を追加  
SassCompiler::run("scss/", "css/");
```

3. SCSS格納ディレクトリを作成
```
public/直下にscssというディレクトリを作成します。
```

4. composerからSassのインストールを実行
```
$ composer update
```