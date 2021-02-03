---
description: Protocole de liaison dans un LAN
---

# Ethernet

* Technologie LAN la plus importante
* Initialement conçu comme bus, sur un câble coaxial partagé 
* Aujourd’hui principalement en étoile, avec un switch qui interconnectent les stations

![Diff&#xE9;rents types de c&#xE2;bles ethernet](../.gitbook/assets/image%20%2862%29.png)

## Câblage

### UTP \(Unshielded Twisted Pair\)

* Comprend 4 paires torsadées non blindées
* En 10 Mb/s et 100 Mb/s, seulement 2 paires sont utilisés
* En Gb-Ethernet, 4 paires sont utilisés
*  Longueur jusqu’à 100 m

![](../.gitbook/assets/image%20%2834%29%20%281%29.png)

### Croisement

La paire de transmission de la source doit être la paire de réception du destinataire **\(T ↔ R\)**

Les switches effectuent un croisement interne des paires

![Connexion PC &#x2194; routeur](../.gitbook/assets/image%20%2867%29.png)

![Connexion routeur &#x2194; routeur](../.gitbook/assets/image%20%286%29.png)

## Trames Ethernet

* Ethernet \(émetteur\) reçoit les données de la couche supérieure et les encapsule dans une trame Ethernet
*  Ethernet \(récepteur\) reçoit la trame de la couche physique, contrôle les en-têtes et passe les données à la couche supérieur
* Une trame ethernet a une longueur minimum de 64 octets

Il existe deux formats incompatibles:

![Trame Ethernet 2](../.gitbook/assets/image%20%2819%29.png)

![Trame 802.3](../.gitbook/assets/image%20%28103%29.png)

### Ethernet 2

#### Préambule et délimiteur

* 7 octets 10101010, dernier octet 10101011
* Permet au récepteur de synchroniser son horloge pour garantir la bonne réception

#### Adresse MAC destination

* La carte réseau du récepteur vérifie si la trame est adressée à son adresse MAC
* Les switches utilisent l’adresse MAC de destination pour envoyer la trame sur la bonne interface de sortie

#### Adresse MAC source

* Permet au récepteur de répondre à l’émetteur

#### Type

* Indique le protocole de la couche supérieure

#### Données

* Une trame peut transporter jusqu’à 1500 octets de données 
* Les données doivent avoir une longueur minimum de 46 octets
* Si les données sont plus courtes de 46 octets, des octets de remplissage \(pad\) sont ajoutées

#### Somme de contrôle \(frame control sequence\)

* La trame se termine par une somme de contrôle sur 32 bits
* Elle est calculé par l’algorithme CRC-32
* Les récepteurs et les switches intermédiaires la vérifient et éliminent les trames erronées
* Ethernet n’effectue pas de retransmission de trames erronées

