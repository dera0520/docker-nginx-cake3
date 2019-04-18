# docker-nginx-cake3
dockerをつかって、nginx,cakephp3 の環境を作りました。

## 証明書の作成
開発用の鍵ファイルを先に作成してください。
やらないと、nginxが立ち上がりません。

``` shell
cd infla/nginx/key
openssl genrsa 2048 > server.key
openssl req -new -key server.key -subj "/C=JP/ST=Tokyo/L=Chuo-ku/O=RMP Inc./OU=web/CN=localhost" > server.csr
openssl x509 -in server.csr -days 3650 -req -signkey server.key > server.crt
```

## Composer Install
プロジェクトはとってきたままなので、ホストマシンで`composer install` を実行してください。