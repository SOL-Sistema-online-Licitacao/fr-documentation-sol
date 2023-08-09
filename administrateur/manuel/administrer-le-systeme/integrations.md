# Intégrations

Dans l'onglet "Intégration", accessible via le menu principal en haut de la page, vous pouvez voir une liste de toutes les intégrations dans le système, modifier leurs informations et forcer l'intégration.&#x20;

SOL vérifie les informations du système qui a été intégré et met à jour les informations sur l'adhésion, l'accord et les éléments de coût dans la base de données.

{% hint style="info" %}
Fréquence d'intégration :&#x20;

Pour planifier la tâche de mise à jour de la base de données dans l'intégration, une expression cron est utilisée pour créer la récurrence.

[https://crontab.cronhub.io/](https://crontab.cronhub.io/)
{% endhint %}

<figure><img src="../../../.gitbook/assets/int.png" alt=""><figcaption></figcaption></figure>

## Comment modifier une intégration ?&#x20;

Pour modifier une intégration, cliquez simplement sur la modification disponible à côté du nom de l'intégration dans la liste de l'onglet "Intégrations".

<figure><img src="../../../.gitbook/assets/int-upd.png" alt=""><figcaption></figcaption></figure>

Effectuez ensuite les modifications nécessaires à l'aide de points de terminaison et de jetons valides, puis cliquez sur "Enregistrer". Les modifications seront enregistrées et l'intégration sera mise à jour.&#x20;

## Comment forcer l'intégration ?&#x20;

Pour forcer une intégration, vous devez d'abord modifier l'intégration à l'aide des points de terminaison et des jetons requis, puis cliquer sur forcer l'intégration, ainsi le statut passera à "En cours".
