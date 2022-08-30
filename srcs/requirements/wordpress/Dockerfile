FROM debian:buster

EXPOSE 9000

WORKDIR etc/wordpress

RUN apt-get update && apt-get upgrade
RUN apt-get -y install php7.3 php-mysqli php-fpm wget sendmail

COPY ./conf/app.conf etc/php/7.3/fpm/pool.d
COPY ./tools /var/www/

RUN chmod +x /var/www/conf.sh

ENTRYPOINT ["sh", "/var/www/conf.sh"]
