EC-CUBE2 Docker Image
=====================

EC-CUBE2 を実行するために必要な設定・extを事前に導入済みのイメージです。

GitHub
[Code](https://github.com/ec-cube2/docker)
[Issues](https://github.com/ec-cube2/docker/issue)

Docker Images
-------------

### PHP 5.6

Nginx + PHP-FRM

`eccube2/php:5.6-fpm` + `eccube2/nginx:latest`

Apache

`eccube2/php:5.6-apache`

### PHP 7.1

Nginx + PHP-FRM

`eccube2/php:7.1-fpm` + `eccube2/nginx:latest`

Apache

`eccube2/php:7.1-apache`

### PHP 7.2

Nginx + PHP-FRM

`eccube2/php:7.2-fpm` + `eccube2/nginx:latest`

Apache

`eccube2/php:7.2-apache`

### PHP 7.3

Nginx + PHP-FRM

`eccube2/php:7.3-fpm` + `eccube2/nginx:latest`

Apache

`eccube2/php:7.3-apache`

### PHP 7.4

Nginx + PHP-FRM

`eccube2/php:7.4-fpm` + `eccube2/nginx:latest`

Apache

`eccube2/php:7.4-apache`


EC-CUBE 2.13
------------

- EC-CUBE 2.13 は PHP 7 で動作しません。
- `ext-mysqli` は利用できません。

### 必須拡張

(*) はベースイメージで導入済み

- ext-ctype (*)
- ext-gd
- ext-mbstring (*)
- ext-session (*)
- ext-zlib (*)

MySQL

- ext-mysql (5.6のみ)
- ext-mysqli

PostgreSQL

- ext-pgsql

### 推奨拡張

(*) はベースイメージで導入済み

- ext-apcu
- ext-curl (*)
- ext-hash (*)
- ext-json (*)
- ext-mcrypt
- ext-opcache
- ext-openssl (*)
- ext-xml (*)
- ext-zip


EC-CUBE 2.17
------------

### 必須拡張

(*) はベースイメージで導入済み

- ext-ctype (*)
- ext-curl (*)
- ext-gd
- ext-json (*)
- ext-mbstring (*)
- ext-libxml (*)
- ext-openssl (*)
- ext-session (*)
- ext-xml (*)
- ext-zip
- ext-zlib (*)

MySQL

`ext-mysqli` の利用を推奨します。

- ext-mysql
- ext-mysqli

PostgreSQL

- ext-pgsql

### 推奨拡張

(*) はベースイメージで導入済み

- ext-apcu
- ext-hash (*)
- ext-mcrypt
- ext-opcache
