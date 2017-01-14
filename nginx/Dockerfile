FROM hypriot/rpi-alpine:3.4

MAINTAINER NGINX Docker Maintainers "docker-maint@nginx.com"

RUN apk update \
    && apk upgrade \
    && apk add nginx \
    && rm -rf /var/cache/apk/*

# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log

RUN mkdir /run/nginx

#VOLUME ["/var/cache/nginx"]

CMD ["nginx", "-g", "daemon off;"]
