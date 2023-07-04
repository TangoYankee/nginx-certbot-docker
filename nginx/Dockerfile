FROM nginx:1.25.1-alpine3.17-slim

RUN apk add certbot certbot-nginx --no-cache
RUN apk add busybox-openrc openrc --no-cache

COPY ./conf.d/ /etc/nginx/conf.d/
# COPY ./cron/cert_renew.sh /etc/periodic/15min/
# COPY ./cron/crontab /etc/crontab
