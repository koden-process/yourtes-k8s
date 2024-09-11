FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

# Mise à jour des paquets et installation des dépendances de base
RUN apt-get update && apt-get install -y \
    software-properties-common \
    curl \
    wget \
    vim \
    unzip \
    git

# Ajout du dépôt pour PHP 5.6
RUN add-apt-repository ppa:ondrej/php \
    && apt-get update

# Installation du module Apache pour PHP 5.6
RUN apt-get install -y libapache2-mod-php5.6

# Installation de PHP 5.6 et des extensions requises
RUN apt-get install -y \
    php5.6 \
    php5.6-cli \
    php5.6-fpm \
    php5.6-mysql \
    php5.6-curl \
    php5.6-json \
    php5.6-cgi \
    php5.6-xml \
    php5.6-mbstring \
    php5.6-zip \
    php5.6-gd

# Copie du fichier de configuration PHP personnalisé
COPY php.ini /etc/php/5.6/apache2/php.ini

# Installation d'Apache et nettoyage des paquets inutiles
RUN apt-get install -y apache2 && apt-get clean

# Activation des modules Apache pour PHP et la réécriture d'URL
RUN a2enmod php5.6
RUN a2enmod rewrite

# Installation de pdftk (outil pour manipuler des PDF) et MySQL client
RUN apt-get install -y pdftk mysql-client

# Exposition du port 80
EXPOSE 80

# Commande de démarrage du serveur Apache
CMD ["apachectl", "-D", "FOREGROUND"]