FROM ubuntu:20.04

RUN apt update \
  && apt install nginx -y \
  && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /run/nginx \
  && chown -R 1001:1001 /run/nginx /var/log/nginx /var/lib/nginx

USER 1001

CMD ["nginx", "-g", "daemon off;"]








