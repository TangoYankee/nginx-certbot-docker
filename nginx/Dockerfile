FROM nginx:1.25.1-alpine3.17-slim

RUN apk add certbot certbot-nginx

COPY ./conf.d/ /etc/nginx/conf.d/
COPY ./cron/cert_renew /etc/periodic/monthly/
