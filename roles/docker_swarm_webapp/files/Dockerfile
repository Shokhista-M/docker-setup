FROM rockylinux:9

RUN dnf -y install epel-release
RUN dnf -y install httpd php mariadb php-mysqlnd
RUN dnf clean all

COPY  lab-app.tgz /tmp/lab-app.tgz

RUN mkdir -p /var/www/html && \
    tar -xzf /tmp/lab-app.tgz -C /var/www/html && \
    chown apache:root /var/www/html/rds.conf.php
    
EXPOSE 80

CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]

