---
description: Les différentes fonctionnalités implémentées avec IPv6
---

# Fonctionnalités

## **Découverte des voisins**

Remplace le protocole ARP et utilise de nouveaux messages ICMPv6:

* Message ‘Sollicitation de voisins’
  * Envoyé à l’adresse multicast ‘All nodes’ du ‘lien’
  * Contient l’adresse IPv6 du nœud cherché
* Message ‘Annonce d’un voisin’
  * Envoyé en réponse à la sollicitation ou spontanément
  * Contient l’adresse IPv6 et MAC du nœud

![](../.gitbook/assets/image%20%28101%29.png)

## **Auto-configuration sans état**

Permet aux machines de configurer leurs adresses IP dans un LAN.

1. La machine construit une adresse local de lien
   * Préfixe FE80::/64 + ID interface EUI-64 modifié
   * Duplicate Address Detection: La machine envoie une Sollicitation de Voisins pour cette adresse. Pas de réponse →OK
2. La machine envoie une **Sollicitation de Routeurs** à l’adresse multicast ‘Tous les routeurs’ du lien
3. Le routeur renvoie une **Annonce de Routeur** avec le préfixe du réseau
4. La machine construit l’adresse globale 
   * Préfixe de réseau + ID interface EUI-64 modifié
   * Duplicate Address Detection: La machine envoie une Sollicitation de Voisins pour cette adresse. Pas de réponse →OK

## Fragmentation

* Contrairement à IPv4, **uniquement la source fragmente des datagrammes**
* Chaque interface IPv6 doit supporter une MTU minimum de 1280 octets
* Découverte de MTU par la source : un routeur qui doit transmettre un datagramme trop long renvoie un message qui indique la MTU permise \(message ICMPv6 «Paquet trop grand\)

![Datagramme IPv6 original](../.gitbook/assets/image%20%287%29.png)

