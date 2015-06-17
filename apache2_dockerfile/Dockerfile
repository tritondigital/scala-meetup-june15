FROM debian:wheezy
MAINTAINER Mike McLean

RUN apt-get -y update
RUN apt-get -y install apache2

COPY files/* /var/www/
RUN chmod +r /var/www/*

RUN sed -i 's|CustomLog ${APACHE_LOG_DIR}/access.log combined|CustomLog /logs/access.log combined|g' /etc/apache2/sites-available/default

EXPOSE 80

ENTRYPOINT ["/usr/sbin/apachectl", "-D", "FOREGROUND"]
