FROM nginx:1.13.10-alpine

# chage time zone 
RUN apk --update add tzdata && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    apk del tzdata && \
    rm -rf /var/cache/apk/*

RUN apk --update add openssl

RUN mkdir -p /var/www/html \
   && chmod 755 -R /var/www/html

ADD nginx.conf /etc/nginx/
