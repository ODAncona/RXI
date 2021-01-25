---
description: Le processus indiquant le chemin à suivre pour un paquet
---

# Acheminement

Il faut distinguer acheminement et routage

#### Acheminement

* Fonctionnalité du protocole IP
* IP utilise la table de routage pour déterminer le prochain saut
* Exécutée pour chaque paquet \(rapide !\)

#### Routage

* Fonctionnalité des protocoles de routage, comme RIP
* Remplir la table de routage avec les routes optimales
* Exécutée périodiquement pour mettre à jour les tables de routage \(lente!\)

## Acheminement

Comment un routeur achemine-t-il un paquet IP ?

* Chaque paquet IP contient l’adresse de destination
* Le routeur a une table de routage
* Le routeur cherche dans sa table l’entrée pour le réseau de destination
* Si aucune route trouvée:
  * Utiliser la route par défaut, s’il y en a
  * Écarter le paquet avec une erreur « Non routable »

![Table de routage](../.gitbook/assets/image%20%2827%29.png)

![Table de routage du premier routeur](../.gitbook/assets/image%20%2895%29.png)

### Remise Directe

* Le destinataire se trouve dans le même réseau LAN
* La source / le routeur peut transmettre le paquet au destinataire sans passer par un autre nœud
* La source / le routeur construit une trame Ethernet avec comme adresse MAC destinataire celle du destinataire final

![](../.gitbook/assets/image%20%28130%29.png)

### Remise Indirecte

* Le destinataire se trouve dans un autre réseau
* Il faut passer par un routeur intermédiaire pour atteindre le destinataire
* La source / le routeur construit une trame Ethernet avec comme adresse MAC destinataire celle du prochain nœud

![](../.gitbook/assets/image%20%2897%29.png)





