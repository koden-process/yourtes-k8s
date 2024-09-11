FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    software-properties-common \
    curl \
    wget \
    vim \
    unzip \
    git

RUN add-apt-repository ppa:ondrej/php \
    && apt-get update

RUN apt-get install -y libapache2-mod-php7.4

RUN apt-get install -y \
    php7.4 \
    php7.4-cli \
    php7.4-fpm \
    php7.4-mysql \
    php7.4-curl \
    php7.4-json \
    php7.4-cgi \
    php7.4-xml \
    php7.4-mbstring \
    php7.4-zip \
    php7.4-gd

COPY php.ini /etc/php/7.4/apache2/php.ini

RUN apt-get install -y apache2 && apt-get clean

RUN a2enmod php7.4
RUN a2enmod rewrite

RUN apt-get install -y pdftk

EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"]