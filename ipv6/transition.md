---
description: Comment passer de IPv4 à IPv6
---

# Transition à IPv6

IPv4 et IPv6 vont coexister pendant une longue durée. Il existe plusieurs méthodes afin de remplacer petit à petit IPv4.

### Méthodes de transition:

1. **Double-pile IPv4 et IPv6**
   * Les machines utilisent IPv4 et IPv6 en parallèle
   * DNS indique s’il faut communiquer en IPv6 ou IPv4
2. **Tunneling**
   * Permet aux réseaux IPv6 de communiquer à travers un réseau intermédiaire IPv4
   * Méthode 6to4 : encapsulation automatique de paquets IPv6 en paquets IPv4
3. **Proxies et translation pour machines sans IPv4**
   * Après l’épuisement des adresses IPv4, l’interopérabilité entre IPv4 et IPv6 nécessite la traduction de paquets

## Double-pile IPv4 et IPv6

* Permet la compatibilité entre IPv4 et IPv6
* Une machine a des adresses IPv4 et IPv6
  * Un hôte double pile peut communiquer avec des hôtes IPv4, IPv6 et double pile
* Son réseau doit également supporter IPv6 \(routeurs IPv6, ISP IPv6\)
* Comment choisir la version d’IP à utiliser ?
  * DNS répond à une requête avec une adresse IPv4, IPv6 ou les deux

![](../.gitbook/assets/image%20%2812%29.png)

## Tunneling

## Proxies et translation pour machines sans IPv4



