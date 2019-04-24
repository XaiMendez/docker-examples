FROM centos:latest

LABEL version=1.0
LABEL description="Beryllium Web App"
LABEL vendor="Xavier Mendez"

MAINTAINER Xavier Mendez <xavier.mendez@tminnova.com>

RUN \ 
  yum -y install \
  httpd \
  php \
  php-cli \
  php-common \
  mod_ssl \
  openssl
  

WORKDIR /var/www/html

RUN echo "<?php phpinfo() ?>" > ./info.php

COPY beryllium .

COPY mysite.key /mysite.key

COPY mysite.crt /mysite.crt

COPY ssl.conf /etc/httpd/conf.d/default.conf

EXPOSE 443

# run apache in forefround
CMD apachectl -DFOREGROUND
