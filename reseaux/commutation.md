---
description: La commutation est le processus d’acheminement de données à travers un réseau.
---

# Commutation

## Commutation de circuits

![](../.gitbook/assets/image%20%2840%29.png)

* Etablissement d’un circuit par des commutateurs avant la transmission des données
* Transmission d’un signal analogique ou d’un flux continu de bits
* Utilisé dans les réseaux téléphoniques 
  * Etablissement du circuit est rapide par rapport à la conversation 
  * Qualité et délai de transmission constants
* Mal adapté aux réseaux informatiques
  * Courts échanges de données avec pauses longues

| Avantages | Inconvénients |
| :--- | ---: |
| Temps de transit très court | Courts échanges de données avec pauses longues |
| Qualité de transmission constante | Non résistante aux pannes |
| Etablissement d'un circuit  est rapide |  |

## Commutation de Paquets

![](../.gitbook/assets/image%20%28119%29.png)

* La source segmente le message à transmettre en paquets
* Les éléments du réseau transmettent les paquets l’un après l’autre de manière indépendante
* Le destinataire recombine les paquets reçus pour obtenir le message

| Avantages | Inconvénients |
| :--- | ---: |
| Utilisation économique de la ligne | Délai de transfert variable et plus long |
| Reroutage facile en cas de panne d’un lien | Pertes de paquets possibles |
| Conversion des formats possibles | Nœuds intermédiaires doivent effectuer des opérations complexes |

