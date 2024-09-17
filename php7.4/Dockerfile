FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    software-properties-common \
    curl \
    wget \
    vim \
    unzip \
    git

RUN apt-get update

RUN apt-get install -y libapache2-mod-php7.4 --fix-missing

RUN apt-get install -y php7.4
RUN apt-get install -y php7.4-cli
RUN apt-get install -y php7.4-fpm
RUN apt-get install -y php7.4-mysql
RUN apt-get install -y php7.4-curl
RUN apt-get install -y php7.4-json
RUN apt-get install -y php7.4-cgi
RUN apt-get install -y php7.4-xml
RUN apt-get install -y php7.4-mbstring
RUN apt-get install -y php7.4-zip
#RUN apt-get install -y libtiff5 php7.4-gd

COPY php.ini /etc/php/7.4/apache2/php.ini

RUN apt-get install -y apache2 && apt-get clean

RUN a2enmod php7.4
RUN a2enmod rewrite

RUN apt-get install -y pdftk

EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"]