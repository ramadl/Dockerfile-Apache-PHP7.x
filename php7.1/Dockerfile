FROM alpine:3.7

LABEL maintainer="RamaDL ramirodldeveloper@gmail.com" 

WORKDIR /shared


ADD https://repos.php.earth/alpine/phpearth.rsa.pub /etc/apk/keys/phpearth.rsa.pub

RUN echo "https://repos.php.earth/alpine/v3.7"  >> /etc/apk/repositories \
    && mkdir /run/apache2 \
    && addgroup -S httpd \ 
    && adduser -S httpd -G httpd \
    && chown httpd /run/apache2 \
    && chgrp httpd /run/apache2 \
    && apk add --no-cache apache2 \ 
    libressl2.6-libcrypto \
    php7.1-apache2 \
    php7.1


COPY ./httpd.conf /etc/apache2/httpd.conf
 

EXPOSE 80

CMD ["httpd", "-D", "FOREGROUND"]
