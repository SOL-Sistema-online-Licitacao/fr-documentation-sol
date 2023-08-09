# Installation frontale

## Préparation de l'environnement

&#x20;Il est nécessaire d'installer certains outils. Cliquez sur les liens ci-dessous pour inciter chacun d'entre eux.

[![YARN](https://img.shields.io/badge/Yarn-2C8EBB.svg?style=for-the-badge\&logo=Yarn\&logoColor=white)](https://yarnpkg.com/cli/install)[![NodeJS](https://img.shields.io/badge/node.js-%2343853D.svg?style=for-the-badge\&logo=node.js\&logoColor=white)](https://nodejs.org/en/)

## Configuration du fichier d'environnement (.env)&#x20;

Dans le répertoire src/enviroments/ il faut changer le fichier environment.prod.ts.

<figure><img src="../.gitbook/assets/arquivos (1).webp" alt=""><figcaption></figcaption></figure>

Modifier les paramètres :

```
encrypt_key: a mesma utiliazada na API
api server e port
```

## Publier le frontend avec Nginx&#x20;

Accédez au répertoire racine de l'API et exécutez la commande ci-dessous :

<pre><code><strong>λ ng build --c production
</strong></code></pre>

#### configurer nginx&#x20;

Vous pouvez vérifier que nginx est opérationnel avec :

```
sudo systemctl restart nginx
sudo systemctl status nginx
```

CONFIGURATION NGINX&#x20;

La configuration de la section précédente est aussi simple que possible. Il écoutera sur le port HTTP 80 tout nom d'hôte qui n'a pas déjà été intercepté. Idéalement, spécifiez un nom\_serveur, ajoutez SSL, redirigez HTTP vers HTTPS.&#x20;

Vous pouvez également envisager de rediriger les non-www vers www, d'ajouter une mise en cache ou d'inclure une limitation de débit.&#x20;

Nginx peut faire toutes ces choses.

```
# /etc/nginx/conf.d/mysife.conf

server {
  listen 0.0.0.0:80;
  root /srv/mysite;
  location / {
    try_files $uri $uri/ /index.html;
  }
}
```
