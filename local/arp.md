---
description: Address Resolution Protocol
---

# ARP

ARP: Address Resolution Protocol

* Trouve l’adresse MAC qui correspond à une adresse IP
* Utilisé à l’intérieur d’un réseau LAN

#### Fonctionnement

ARP possède un cache \(adresse IP, adresse physique\)

* Requête ARP en diffusion si l’adresse IP n’est pas dans le cache
* La machine concernée répond avec son adresse physique
* Les entrées du cache sont éliminées si elles ne sont pas rafraîchies \(toutes les 20 min\)

![](../.gitbook/assets/image%20%2837%29.png)

