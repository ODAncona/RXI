---
description: Adresse physique d’une carte réseau
---

# MAC Adresse

![adresse MAC](../.gitbook/assets/image%20%2874%29.png)

La MAC adresse est l'adresse physique d’une interface réseau. Elle peut être:

* **Unique**: Toutes les cartes réseau ont une adresse différente
* **Fixe** : configurée dans la mémoire ROM de la carte

#### Format

48 bits en notation hexadécimale. \(00:00:0A:BB:28:FC\)

#### Structure

3 premiers octets : Identification du constructeur

* 00:00:0C:xx:xx:xx: Cisco
* 00:02:B3:xx:xx:xx: Intel

3 derniers octets : Identification de la carte \(gérée par le constructeur\)

Le bit le moins significatif du premier octet indique une adresse de groupe

![Le LSB du premier octet indique une adresse de groupe](../.gitbook/assets/image%20%2847%29.png)

### Adresse broadcast \(FF:FF:FF:FF:FF:FF\)

* Les cartes réseau écoutent cette adresse et les stations doivent traiter les trames reçues 
* Utilisé par exemple pour requêtes DHCP



