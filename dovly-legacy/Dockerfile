#dovly-legacy:dev
# FROM ubuntu:bionic as dovly-legacy
FROM phusion/baseimage as dovly-legacy
MAINTAINER Khoa Nguyễn khoa002@gmail.com
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -y update && apt-get -y install --no-install-recommends apt-utils
RUN apt-get -y update && apt-get -y install software-properties-common
RUN add-apt-repository ppa:ondrej/php
RUN apt-get -y update && apt-get install -y \
apache2 \
php7.2 \
libapache2-mod-php7.2 \
php7.2-mbstring \
php7.2-mysqli \
php7.2-xml \
php7.2-zip \
mcrypt \
nano \
curl
RUN curl -s https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
COPY conf/digmeout.conf /etc/apache2/sites-available/
RUN a2dissite 000-default.conf
RUN a2ensite dovly-legacy.conf
RUN a2enmod rewrite
RUN a2enmod headers
RUN chgrp -R www-data /var/www
RUN find /var/www -type d -exec chmod 775 {} +
RUN find /var/www -type f -exec chmod 664 {} +
EXPOSE 80
CMD ["/usr/sbin/apache2ctl","-DFOREGROUND"]