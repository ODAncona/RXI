---
description: 'Garantie de délivrance des données, dans l’ordre de l’émission'
---

# Transmission Fiable

#### Mécanismes nécessaires:

1. Numéros de séquence
2. Acquittement
3. Retransmission

TCP détecte la perte de paquets par deux événements:

#### Timeout du temporisateur de retransmission

* Aucun acquittement n’a été reçu
* C’est-à-dire plusieurs paquets ont été perdus
* Signale typiquement une congestion sévère

#### Trois acquittement dupliqués

* Un ou plusieurs paquets ont été perdus
* Mais quelques paquets sont arrivés correctement
* Signale une congestion légère

## Format des paquets TCP

![Les flags servent &#xE0; signaler le type de paquet trait&#xE9;.](../../.gitbook/assets/image%20%2863%29.png)

### Bits

* URG = urgent
* ACK = acquittement \(message contient un acquittement\)
* RST = reset \(recommencer lors d'une erreur\)
* SYN = synchronisation \(établissement de connexion\)
* FIN = fin de transmission
* PSH = push \(envoyer les données immédiatement \)

### Numéros de séquence

* Les octets sont numérotés, non pas les segments
* L’émetteur indique le numéro du premier octet des données du segment

### Acquittement

* Le numéro d’acquittement indique le **prochain octet attendu par le récepteur**
* Un acquittement peut être envoyé séparément ou combiné avec des données
* Les acquittements sont **cumulatifs**

{% hint style="info" %}
Un acquittement confirme la réception de toutes les données jusqu’à ce point
{% endhint %}

### Retransmission

* L’émetteur gère un temporisateur de retransmission pour chaque segment envoyé
* Si le temporisateur expire avant la réception d’un acquittement, le segment est retransmis
* TCP a un mécanisme pour adapter la durée du temporisateur

![Retransmission demand&#xE9;e par l&apos;expiration du temporisateur](../../.gitbook/assets/image%20%2852%29.png)

### Retransmission rapide

Un segment intermédiaire a été perdu, comment signaler que les segments suivants sont arrivés ?

![Processus de retransmission rapide](../../.gitbook/assets/image%20%2835%29.png)

* Lors de la réception d’un segment en désordre, le récepteur répète le dernier ACK \(‘ACK dupliqué’\)
* Si l’émetteur reçoit 3 ACK dupliqués, il retransmet le segment sans attendre un timeout

