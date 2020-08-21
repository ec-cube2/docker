EC-CUBE2 Nginx Docker Image
=====================

EC-CUBE2 を実行するために必要な設定済みのイメージです。

GitHub
[Code](https://github.com/ec-cube2/docker)
[Issues](https://github.com/ec-cube2/docker/issue)


設定
----

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
