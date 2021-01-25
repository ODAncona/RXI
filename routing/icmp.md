---
description: Internet Control Message Protocol
---

# ICMP

ICMP est un protocole de niveau 3 encapsulé dans un datagramme IP qui permet le contrôle des erreurs de transmission. Il permet de :

* Communiquer des problèmes
* Effectuer des diagnostiques

![Le message ICMP est encapsul&#xE9; dans un datagramme IP](../.gitbook/assets/image%20%28137%29.png)

#### Types de messages ICMP

| Type | Message provoqué | Description |
| :--- | :--- | :--- |
| 0, 8 | Echo request & reply | Ping |
| 3 | Destination Unreachable \(network/host\) | Routage impossible |
| 5 | Redirect | Il existe un meilleur chemin |
| 11 | Time exceeded | TTL = 0 |

#### Ping

Vérifier la connectivité et le bon fonctionnement d’un système.

#### Problèmes de routage \(ICMP type 3\)

* Code 0: envoyé par le routeur s’il n’y a pas de route ou s’il la fragmentation est nécessaire mais interdite
* Code 1: envoyé par le routeur lors de la remise directe si la machine ne répond pas à la requête ARP

