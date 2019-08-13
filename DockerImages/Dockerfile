FROM ubuntu

RUN apt-get update && \
    apt-get install nginx -y && \
    apt-get install php7.0 -y && \
    apt-get install -y wget && \
    apt-get install htop && \
    ln -sf /dev/stdout /var/log/nginx/access.log && \
    ln -sf /dev/stderr /var/log/nginx/error.log

WORKDIR /etc/nginx/sites-enabled

COPY default default

WORKDIR /var

RUN mkdir downloads

WORKDIR /downloads

RUN wget https://github.com/dockerfile/nginx/archive/master.zip

COPY source /var/www/html

VOLUME ["/var/www/html"]

EXPOSE 81

CMD ["nginx", "-g", "daemon off;"]