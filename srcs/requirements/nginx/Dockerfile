FROM alpine:3.15

WORKDIR etc/nginx/ssl

RUN apt-get update && apt-get upgrade
RUN apt-get install -y nginx openssl
RUN openssl req -newkey rsa:4096 -x509 -sha256 -days 365 -nodes \
        -out /etc/nginx/ssl/svalenti.pem \
        -keyout /etc/nginx/ssl/svalenti.key \
        -subj "/C=IT/ST=Rome/L=Rome/O=42 School/OU=svalenti/CN=svalenti/"

COPY ./conf/app.conf etc/nginx/config/nginx.conf

EXPOSE 443

ENTRYPOINT ["nginx", "-g", "daemon off;"]
