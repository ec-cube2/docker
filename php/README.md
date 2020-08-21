EC-CUBE2 PHP Docker Image
=========================

EC-CUBE2 を実行するために必要な設定・extを事前に導入済みのイメージです。

GitHub
[Code](https://github.com/ec-cube2/docker)
[Issues](https://github.com/ec-cube2/docker/issue)


php:* イメージとの違い
--------------------

以下の拡張が導入済みです。

- ext-apcu
- ext-gd
- ext-mcrypt (5.6のみ)
- ext-mysql (5.6のみ)
- ext-mysqli
- ext-opcache
- ext-pgsql
- ext-zip

Composer を導入済みです。

PHP 5.6 / 7.1 のベースイメージは更新されないため、 apt-get upgrade を行います。


設定
----

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
