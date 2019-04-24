### Beryllium Web Application
This is a image based in Dockerfile.

- centos
- apache
- php
- openssl

#### Creating SSL key and crt
$ openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout mysite.key -out mysite.crt

#### Create image
$ docker build -t app-web-beryllium-ssl:1.0 .

#### Create container
$ docker run -d --name app-web-beryllium-ssl -p 81:443 app-web-beryllium-ssl:1.0
