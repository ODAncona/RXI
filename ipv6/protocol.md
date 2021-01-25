---
description: ou comment adresser toutes les fourmis du monde entier
---

# Protocole IPv6

### Objectifs

* Fournir suffisamment d’adresses, même avec une allocation très inefficace
* Rendre plus efficace le traitement des paquets par les routeurs
* Mieux structurer les protocoles annexes à IP \(ICMP, ARP, …\)
* Rendre le protocole plus évolutif

### Caractéristiques principales d’IPv6

1. Adresses sur 128 bits au lieu de 32 bits dans IPv4
2. En-tête simplifié
   * Pas de fragmentation par les routeurs
3. Extensibilité de l’en-tête par des options 
4. Nouvelles fonctionnalités 
   * Auto-configuration d’adresses des machines \(sans DHCP\)
   * Découverte de la MTU le long d’une route
5. ARP, ICMP, IGMP remplacés par **ICMPv6**

### Notations

* 8 groupes de 4 chiffres hexadécimaux, séparés par ‘:’
* Exemple: 2001:AB75:4345:4A45:AF3F:3255:F431:A44B

### Simplification

* Les premiers 0 d’un groupe peuvent être omis:
  * A12 au lieu de 0A12
* Plusieurs groupes 0 peuvent être remplacés par ‘::’ 
  * 2010:**0:0:0:0**:800:200C:2342 → 2010**::**800:200C:2342
  * 0:0:0:0:0:0:0:1 → ::1





