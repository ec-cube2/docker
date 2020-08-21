FROM nginx:latest

COPY default.conf /etc/nginx/conf.d/default.conf

# entrypoint
COPY docker-nginx-entrypoint /usr/local/bin/

ENTRYPOINT ["docker-nginx-entrypoint"]
CMD ["nginx", "-g", "daemon off;"]
