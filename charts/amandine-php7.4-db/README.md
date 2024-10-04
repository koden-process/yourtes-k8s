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

# Helm de déploiement d'Amandine PHP 7.4

**Déploiement**
```sh
 helm install app-amandine-74 ./app-amandine-7.4 -f app-amandine-7.4/values_sample.yaml
```

**Suppression**
```sh
helm uninstall app-amandine-74 -n <namespace>
```


Source de données
https://artifacthub.io/packages/helm/bitnami/mariadb