# Installation de l'API

## Préparation de l'environnement

&#x20;Il est nécessaire d'installer certains outils. Cliquez sur les liens ci-dessous pour inciter chacun d'entre eux.

[![YARN](https://img.shields.io/badge/Yarn-2C8EBB.svg?style=for-the-badge\&logo=Yarn\&logoColor=white)](https://yarnpkg.com/cli/install)[![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge\&logo=docker\&logoColor=white)](https://docs.docker.com/compose/install/#install-compose)[![NodeJS](https://img.shields.io/badge/node.js-%2343853D.svg?style=for-the-badge\&logo=node.js\&logoColor=white)](https://nodejs.org/en/)[![PM2](https://img.shields.io/badge/PM2-2B037A.svg?style=for-the-badge\&logo=PM2\&logoColor=white)](https://www.npmjs.com/package/pm2)

## Configuration du fichier d'environnement (.env)&#x20;

Accédez au répertoire racine de l'API et exécutez la commande ci-dessous :

```
λ docker-compose up -d
```

Créez un fichier prod.env dans le dossier /env de l'API au format suivant :

```
PORT=4002
NOSQL_CONNECTION_STRING=mongodb://localhost:20000/lacchain
JWT_KEY=secret_KEY
JWT_REFRESH_TOKEN_KEY=****************==
JWT_ACCESS_TOKEN_EXPIRATION=8h
JWT_REFRESH_TOKEN_EXPIRATION=7d
ENCRYPT_KEY=********-****-****-****-************
SENDGRID_EMAIL_SENDER=email@email.com
SENDGRID_API_KEY=******************

AWS_REGION=us-east-1
AWS_ACCESS_KEY_ID=******************
AWS_SECRET_ACCESS_KEY=**********/********/****

S3_BUCKET=dev-sol-app-api
S3_BUCKET_DOCUMENTS=dev-sol-app-api
S3_BUCKET_ANNOUNCEMENT_PHOTO=dev-sol-app-api                                    
```

Description des paramètres du fichier env :

<table><thead><tr><th width="378">Descrição</th><th>Parâmetro</th></tr></thead><tbody><tr><td>PORT</td><td>Port sur lequel l'API sera lancée</td></tr><tr><td>NOSQL_CONNECTION_STRING</td><td>Chaîne de connexion à la base de données, ici le chemin publié par docker compose doit être ajouté.</td></tr><tr><td>JWT_KEY</td><td>Clé utilisée pour le chiffrement JWT</td></tr><tr><td>JWT_REFRESH_TOKEN_KEY</td><td>Clé utilisée pour vérifier l'authenticité des jetons de rafraîchissement JWT</td></tr><tr><td>JWT_ACCESS_TOKEN_EXPIRATION</td><td>Heure d'expiration du jeton JWT</td></tr><tr><td>JWT_REFRESH_TOKEN_EXPIRATION</td><td>Délai d'expiration du jeton d'actualisation JWT</td></tr><tr><td>ENCRYPT_KEY</td><td>Clé utilisée pour le chiffrement de la charge utile. Il doit être généré par l'utilisateur et il doit être conforme au frontend.</td></tr><tr><td>SENDGRID_EMAIL_SENDER</td><td>E-mail source pour les services SendGrid</td></tr><tr><td>SENDGRID_API_KEY</td><td>Clé utilisée pour authentifier et autoriser l'accès aux ressources du service SendGrid</td></tr><tr><td>AWS_REGION</td><td>Région du serveur AWS (Null si vous n'utilisez pas AWS)</td></tr><tr><td>AWS_ACCESS_KEY_ID</td><td>Clé d'accès AWS</td></tr><tr><td>AWS_SECRET_ACCESS_KEY</td><td>Autenticador de acesso para serviços AWS</td></tr><tr><td>S3_BUCKET</td><td>Authentificateur d'accès pour les services AWS</td></tr><tr><td>S3_BUCKET_DOCUMENTS</td><td>Authentificateur d'accès pour les services AWS</td></tr><tr><td>S3_BUCKET_ANNOUNCEMENT_PHOTO</td><td>Authentificateur d'accès pour les services AWS</td></tr></tbody></table>

## Publication de l'API&#x20;

Accédez au répertoire racine de l'API et exécutez la commande ci-dessous :

```
λ yarn publish:prod
```

Yarn créera un package contenant tout le code source du package, ainsi que le fichier "package.json" mis à jour avec la version.

## &#x20;Installer PM2 sur le serveur&#x20;

Documents PM2 :

[https://pm2.keymetrics.io/docs/usage/pm2-doc-single-page/](https://pm2.keymetrics.io/docs/usage/pm2-doc-single-page/)

Exécutez la commande :

```
λ npm install pm2@latest -g
```

## Exécution PM2

Exécutez la commande :

```
λ pm2 start npm --name "sol-api-dev" -- run "start:dev"
```

## lancer la semence&#x20;

La graine crée l'utilisateur administratif et une association.

```
λ yarn run seed
```
