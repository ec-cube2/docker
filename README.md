EC-CUBE2 Docker Image
=====================

EC-CUBE 2 を実行するために必要な ext を事前に導入済みのイメージです。

GitHub
[Code](https://github.com/ec-cube2/docker)
[Issues](https://github.com/ec-cube2/docker/issue)


PHP
---

以下の拡張が導入済みです。

- ext-apcu
- ext-gd
- ext-mcrypt (5.6のみ)
- ext-mysql (5.6のみ)
- ext-mysqli
- ext-opcache
- ext-pgsql
- ext-zip


以下の環境変数でPHPの設定が可能です。

| ENV | ini | Default |
| --- | --- | --- |
| TZ | date.timezone |
| PHP_MEMORY_LIMIT | memory_limit |
| PHP_DISPLAY_ERRORS | display_errors Off |
| PHP_MAX_INPUT_VARS | max_input_vars |
| PHP_EXPOSE_PHP | expose_php | Off |
| PHP_MAX_EXECUTION_TIME | max_execution_time |
| PHP_POST_MAX_SIZE | post_max_size |
| PHP_UPLOAD_MAX_FILESIZE | upload_max_filesize |

Configure OPcache for Maximum Performance

| ENV | ini | Default |
| --- | --- | --- |
| PHP_OPCACHE_MEMORY_CONSUMPTION | opcache.memory_consumption |
| PHP_OPCACHE_MAX_ACCELERATED_FILES | opcache.max_accelerated_files |

Don't Check PHP Files Timestamps

| ENV | ini | Default |
| --- | --- | --- |
| PHP_OPCACHE_VALIDATE_TIMESTAMPS | opcache.validate_timestamps |

Configure the PHP realpath Cache

| ENV | ini | Default |
| --- | --- | --- |
| PHP_REALPATH_CACHE_SIZE | realpath_cache_size |  |
| PHP_REALPATH_CACHE_TTL | realpath_cache_ttl |  |

PHP-FPM は以下も設定可能です。

; から始まるものはデフォルト値は有効になっていません。

| ENV | ini | Default |
| --- | --- | --- |
| PHPFPM_PM_MAX_CHILDREN | pm.max_children | 5 |
| PHPFPM_PM_START_SERVERS | pm.start_servers | 2 |
| PHPFPM_PM_MIN_SPARE_SERVERS | pm.min_spare_servers | 1 |
| PHPFPM_PM_MAX_SPARE_SERVERS | pm.max_spare_servers | 3 |
| PHPFPM_PM_STATUS_PATH | pm.status_path | ;/status |
| PHPFPM_PING_PATH | ping.path | ;/ping |
| PHPFPM_REQUEST_TERMINATE_TIMEOUT | request_terminate_timeout | ;0 |


Nginx
-----

EC-CUBEデフォルトで必要な設定が含まれています。

以下は環境変数で設定可能です。

| ENV | conf | Default |
| --- | --- | --- |
| NGINX_SERVER_NAME | server_name | localhost |
| NGINX_ROOT | root | /usr/share/nginx/html |
| NGINX_REAL_IP_HEADER | real_ip_header |  |
| NGINX_SET_REAL_IP_FROM | set_real_ip_from |  |
| FASTCGI_PASS | fastcgi_pass | 127.0.0.1:9000 |
| FASTCGI_READ_TIMEOUT | fastcgi_read_timeout | 60 |
| FASTCGI_SEND_TIMEOUT | fastcgi_send_timeout | 60 |
| FASTCGI_BUFFERS | fastcgi_buffers | 8 8k |
| FASTCGI_BUFFER_SIZE | fastcgi_buffer_size | 8k |


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

Alpine は？
-----------------

See https://qastack.jp/superuser/1219609/why-is-the-alpine-docker-image-over-50-slower-than-the-ubuntu-image
