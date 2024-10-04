# Amandine php 7.4 

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