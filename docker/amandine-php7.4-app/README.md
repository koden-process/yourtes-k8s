# Amandine php 7.4 

## Docker

**build**
```sh
docker build -t amandine-7.4 .
docker build --platform linux/amd64 -t killiankopp/amandine-7.4:latest .
```

**run**
```sh
docker run \
--env=DEBIAN_FRONTEND=noninteractive \
--volume=/Users/killian/Koden/sandbox/cd-interieur.fr/www:/var/www/html \
--network=bridge \
-p 80:80 \
--restart=no \
--name cd-interieur \
-d amandine-7.4:latest
```