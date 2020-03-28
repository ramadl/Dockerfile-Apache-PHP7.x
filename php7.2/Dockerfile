FROM alpine:3.9

LABEL maintainer="RamaDL ramirodldeveloper@gmail.com" 

WORKDIR /shared

RUN mkdir /run/apache2 \
    && addgroup -S httpd \ 
    && adduser -S httpd -G httpd \
    && chown httpd /run/apache2 \
    && chgrp httpd /run/apache2 \
    && apk add --no-cache   apache2 \ 
                            php7-apache2 \
                            php7

COPY ./httpd.conf /etc/apache2/httpd.conf

EXPOSE 80

CMD ["httpd", "-D", "FOREGROUND"]