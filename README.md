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
<!-- composer create-project "laravel/laravel=~6.0" --prefer-dist laravelapp -->

## .envファイル修正
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel_db
DB_USERNAME=laravel_user
DB_PASSWORD=password

## migrateの実行
```
$ docker exec -it laravel_app bash
$ cd laravelapp
$ php artisan migrate
```
