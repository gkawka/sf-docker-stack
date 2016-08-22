FROM nginx:stable-alpine

RUN apk add --update bash \
 && rm -rf /var/cache/apk/*

COPY vhost.conf /etc/nginx/conf.d/
