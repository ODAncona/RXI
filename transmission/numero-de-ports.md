---
description: Canal utilisé par les applications
---

# Numéro de ports

* Les numéros de ports sont les adresses de la couche Transport
* Permettent d’adresser plusieurs applications sur la même machine
* Entiers sur 16 bits
* Utilisés par TCP et UDP
* TCP et UDP peuvent réutiliser les mêmes ports

![](../.gitbook/assets/image%20%2877%29.png)

## Ports TCP / UDP

#### Ports bien connus \(1-1023\)

* Assignés à des applications standard
* Typiquement utilisés par les applications serveur

| Service | Port | Protocol |
| :--- | :--- | :--- |
| SSH | 22 | TCP |
| SMTP | 25 | TCP |
| DNS | 53 | UDP |
| HTTP | 80 | TCP |
| HTTPS | 443 | TCP |

#### Ports éphémère \(1024-65536\)

* Typiquement utilisés par les applications client
* Assignés dynamiquement par TCP/UDP

