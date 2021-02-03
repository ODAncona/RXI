---
description: l’émetteur adapte le débit en fonction du récepteur
---

# Contrôle de flux

Le contrôle de flux sert à :

* Adapter la vitesse du récepteur
* Eviter qu'un émetteur rapide surcharge un récepteur lent

## Protocole de la fenêtre glissante

Ce protocole permet à l’émetteur d’envoyer plusieurs paquets avant de devoir attendre un accusé de réception.

#### Principe

* Les données dans la fenêtre peuvent être envoyées sans attendre d’acquittement
* La réception d’un acquittement permet de glisser la fenêtre à droite

![La fen&#xEA;tre glisse vers la droite durant la transmission](../../.gitbook/assets/image%20%2830%29.png)

* Basé sur un protocole à fenêtre glissante mais avec une taille de fenêtre variable
* La fenêtre utilisable correspond à la place libre dans le tampon du récepteur
* Chaque accusé de réception indique en plus la taille de la fenêtre \(window advertisement\)

{% hint style="success" %}
En variant la taille de la fenêtre, le récepteur peut contrôler la vitesse de transmission de l’émetteur
{% endhint %}

![Exemple de contr&#xF4;le de flux](../../.gitbook/assets/image%20%2869%29.png)

