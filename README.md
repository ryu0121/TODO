# README

## モノシリックなRails アプリの環境構築

### イメージ構築
`docker-compose build`

### MySQL のplugin を修正(ver8.0 以降の問題)
`docker exec -it container-name(db) bash`(コンテナ名はdocker ps で確認)

`mysql -uroot -p`

`mysql> SELECT user, host, plugin FROM mysql.user;`

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';`

`ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY 'password';`

`SELECT user, host, plugin FROM mysql.user;`

### localhostにアクセス
`docker exec container-name(web) bash`

`rails db:create db:migrate`

localhost に接続