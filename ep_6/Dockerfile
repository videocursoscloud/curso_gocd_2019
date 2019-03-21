FROM ubuntu:latest

RUN apt-get update
RUN apt-get install apache2 -y

EXPOSE 80

ADD index.html /var/www/html/index.html

CMD  apachectl -DFOREGROUND
