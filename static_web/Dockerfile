# Version: 0.0.1
FROM ubuntu:16.04
MAINTAINER Matt Gartman "mattgartman@gmail.com"
RUN apt-get update; apt-get install -y apache2
ENV APACHE_RUN_USER www-data
ENV APPACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
# not in book
ENV APACHE_PID_FILE /var/run/apache2.pid
ENV APACHE_RUN_DIR /var/run/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2

RUN mkdir -p $APACHE_RUN_DIR $APACHE_LOCK_DIR $APACHE_LOG_DIR


ONBUILD ADD . /var/www/
EXPOSE 80
ENTRYPOINT ['/usr/sbin/apache2']
CMD ["-D", "FOREGROUND"]

