FROM ubuntu:18.04

MAINTAINER Enter-Y

RUN apt-get update && apt-get install nginx -y \
        && apt-get clean \
        && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
        && echo "daemon off;" >> /etc/nginx/nginx.conf

ADD vapor-default /etc/nginx/sites-available/default

RUN ln -sf /dev/stdout /var/log/nginx/access.log && \
    ln -sf /dev/stderr /var/log/nginx/error.log

CMD ["nginx"]