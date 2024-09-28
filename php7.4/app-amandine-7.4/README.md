# Helm de déploiement d'Amandine PHP 7.4

**Déploiement**
```sh
helm install app-amandine-74 app-amandine-74 -f app-amandine-74/values_sample.yaml -n sandbox
```

**Suppression**
```sh
helm uninstall app-amandine-74 -n sandbox
```