FROM ubuntu:20.04
ENV DEBIAN_FRONTEND noninteractive

RUN \
    apt-get update &&  \
    apt-get install -y software-properties-common && \
    apt-get update &&  \
    apt-get install -y wget unzip apache2 mariadb-server libapache2-mod-php7.4 php7.4-gd php7.4-mysql php7.4-curl php7.4-mbstring php7.4-intl php7.4-gmp php7.4-bcmath php-imagick php7.4-xml php7.4-zip && \
    apt-get install -i mysql-client

RUN a2enmod php7.4 && a2enmod rewrite

RUN \
    cd /var/www/ && \
    wget https://download.nextcloud.com/server/releases/nextcloud-22.2.2.zip && \
    unzip nextcloud-22.2.2.zip && \
    rm -f nextcloud-22.2.2.zip && \
    chown www-data. -R nextcloud

EXPOSE 80

CMD ["/usr/sbin/apache2ctl", "-DFOREGROUND"]