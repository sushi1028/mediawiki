FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update && apt upgrade -y 
    
RUN apt install -y apache2 \
    mysql-server \
    php php-mysql \
    libapache2-mod-php \
    php-xml \
    php-mbstring

RUN apt install -y software-properties-common wget tar systemd && \
    service apache2  start 

RUN cd /tmp && \
    wget https://releases.wikimedia.org/mediawiki/1.34/mediawiki-1.34.0.tar.gz && \
    mkdir /var/lib/mediawiki && \
    tar -xvzf /tmp/mediawiki-*.tar.gz && \
    mv mediawiki-*/* /var/lib/mediawiki

RUN ln -s /var/lib/mediawiki /var/www/html/mediawiki 

EXPOSE 80

CMD [ "apachectl", "-D", "FOREGROUND" ]

ENTRYPOINT [ "bash" ]