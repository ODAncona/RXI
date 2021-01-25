---
description: les équipements au sein d'un réseau
---

# Types d’équipements

Un réseau informatique comprend des terminaux et des nœuds intermédiaires.

Les **terminaux** typiquement implémentent toutes les couches jusqu’au niveau application.

Les nœuds intermédiaires implémentes uniquement les couches nécessaires pour leur travail

## Switch

* À l’intérieur d’un réseau local d’une entreprise ou à la maison
* Interconnecte les équipements d’un même ‘réseau’ avec un débit élevé \(100 Mb/s – 10 Gb/s\)
* Implémente Ethernet \(couches 1+2\), avec quelques fonctions supplémentaires

## Point d'Accès

* Comme un switch Ethernet, mais pour Wifi
* A l’intérieur d’un réseau local
* Implémente Ethernet \(couches 1+2\)

## Routeur

* A comme fonction principale de trouver pour chaque paquet le meilleur chemin vers le destinataire
* Implémente le protocole IP
  * Examine l’adresse IP de destination de chaque paquet
* Implémente des protocoles de routage
  * Pour remplir la table de routage

## Routeur ADSL

Equipements qui combinent plusieurs fonctions

* Modem pour la connexion à la ligne téléphonique
* Switch Ethernet avec plusieurs interfaces
* Point d’accès Wifi
* Routeur vers le réseau du fournisseur d’accès
* Serveur DHCP
* Firewall

