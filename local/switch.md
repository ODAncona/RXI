---
description: Equipement réseau qui permet de séparer physiquement les terminaux
---

# Switch

![](../.gitbook/assets/image%20%2816%29.png)

* Les réseaux locaux modernes utilisent des switches Ethernet 
* Un switch travaille à la couche 2
  * Il connaît le format des trames et peut interpréter les adresses MAC \(source et destination\)
  * Il reçoit une trame, l’analyse et la transmet plus loin

#### Avantages

* Un canal dédié dans chaque direction
  * Pas de partage du médium
  * Pas de collisions, pas de CSMA
* Chaque interface peut émettre et recevoir en même temps
* Un switch peut transmettre une trame vers le bon destinataire, sans l'envoyer sur les autres ports

#### Fonctions

* Commutation de trames: 
  * Réception, contrôle et envoi de plusieurs trames en parallèle
* Acheminement vers le destinataire:
  *  Apprentissage dynamique de la structure du réseau
* Arbre recouvrant
* Réseaux LAN virtuels
  * Séparation d'un LAN en plusieurs VLAN
* Autres fonctions
  * Power-over-Ethernet \(alimentation électrique des stations\)
  * Mécanisme de sécurité

### Commutation de trames

* Port:
  * Composé d’un récepteur et d’un émetteur
  * Connecté à une matrice de commutation
* Les ports sont indépendants les uns des autres
  * Plusieurs trames peuvent être commutées simultanément
  * Pas de collisions entre les trames de différents ports

![](../.gitbook/assets/image%20%2853%29.png)

### Acheminement de trames

* Un switch Ethernet doit fonctionner sans aucune configuration 
* Un switch essaie d’envoyer les trames seulement en direction du destinataire
* Réduction du trafic sur le réseau

  Nécessite une **table de filtrage** qui indique le port de sortie pour chaque adresse MAC

  * Aussi appelé « table CAM », mais jamais « table de routage »

* Si une adresse MAC destination est inconnue, le switch envoie la trame sur toutes les sorties

#### HUB versus Switch

![Un hub effectue la diffusion des bits sur toutes les sorties](../.gitbook/assets/image%20%2882%29.png)

![Un switch essaie de transmettre les trames uniquement sur la sortie en direction du r&#xE9;cepteur](../.gitbook/assets/image%20%2811%29.png)

