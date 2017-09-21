FROM ubuntu:latest
RUN apt-get update && apt-get -y install apache2 && apt clean && rm -rf /var/lib/apt/lists/*

EXPOSE 80
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data

#ADD monsupersite.tar.gz /usr/local/apache2/htdocs/
VOLUME /var/www/html
ADD 000-default.conf /etc/apache2/sites-available/

CMD ["/usr/sbin/apache2", "-D", "FOREGROUND"]
