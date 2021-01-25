---
description: Modèle utilisé concrètement
---

# Modèle TCP / IP

![Mod&#xE8;le TCP/IP](../.gitbook/assets/image%20%28110%29.png)

* La couche hôte-réseau couvre les couches liaison et physique du modèle OSI
* Les couches session et présentation manquent. Ces fonctions doivent être réalisées par l’application
* Les autres couches sont similaires aux couches respectives du modèle OSI

![Le mod&#xE8;le TCP/IP n&apos;impl&#xE9;mente pas toutes les couches](../.gitbook/assets/image%20%2851%29.png)

## Adressage dans le modèle TCP/IP

#### Adresse MAC \(physique\)

* Adresse physique d’une interface réseau
* Par exemple interface Ethernet ou interface Wifi
* Un ordinateur peut avoir plusieurs adresses MAC, une par interface

#### Adresse IP \(réseau\)

* Adresse logique d’une interface réseau
* Un ordinateur peut avoir plusieurs adresses IP, une par interface et des adresses spéciales

#### Protocole \(transport\)

* En plus de l’adresse IP, il est nécessaire d’indiquer le protocole, par exemple IP

Couche transport

* Chaque protocole a un numéro
* Il suffit d’indiquer le numéro de protocole à qui les données sont destinées – Normalement TCP ou UDP

#### Numéro de port \(application\)

* Une application qui envoie et reçoit des données doit demander un numéro de port a TCP ou UDP
* Chaque application utilisera donc un numéro de port différent
* Certain numéros de port sont réservés pour des services courants comme Web ou Mail

