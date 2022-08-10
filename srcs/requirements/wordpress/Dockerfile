FROM alpine:3.15

EXPOSE 9000

WORKDIR etc/wordpress

RUN apt-get update && apt-get upgrade
RUN apt-get -y install php7.3 php-mysqli php-fpm wget sendmail

COPY ./conf/app.conf etc/php/7.3/fpm/pool.d
COPY ./tools/conf.sh /tmp/confwd.sh

RUN chmod +x /tmp/confwd.sh

ENTRYPOINT ["sh", "/tmp/confwd.sh"]
