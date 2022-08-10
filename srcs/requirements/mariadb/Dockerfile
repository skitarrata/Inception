FROM alpine:3.15

EXPOSE 3306

RUN apt-get update && apt-get upgrade
RUN apt-get install mariadb mariadb-client

COPY ./tools/conf.sh /tmp/conf.sh

RUN chmod +x /tmp/conf.sh

ENTRYPOINT ["sh", "/tmp/conf.sh"]
