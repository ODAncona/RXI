---
description: Réutilisation d'adresse ip
---

# NAT

#### Adressage privé

Avec IP v4 il n'y a pas assez d'adresse disponible pour tout le monde. Alors il est judicieux d'utiliser la même adresse que notre réseau.

#### Traduction des adresses privées

Les adresses privées sont uniques et ne sont donc pas utilisables sur Internet

## NAT Network Address Translation

Nat permet de traduire les adresse privées entre le réseau interne et Internet public.

![Utilisation de l&apos;adresse publique pour les trois terminaux](../.gitbook/assets/image%20%2886%29.png)

### Nat dynamique

* L’équipement NAT dispose d’un pool d’adresses publiques
* Les adresses publiques sont allouées temporairement à une machine dès qu’elle établit une connexion avec l’extérieur
* Le nombre de connexions simultanées est limité par le nombre d’adresses publiques disponibles

![NAT simple](../.gitbook/assets/image%20%2889%29.png)

### Napt \(Network Address Port Translation\)

* Une seule adresse publique est partagée entre plusieurs connexions simultanées
* L’équipement NAT modifie l’adresse source privée ainsi que le port TCP/UDP source du paquet sortant
* Grâce au port source, le NAT peut distinguer les différentes connexions

![Napt](../.gitbook/assets/image%20%2857%29.png)



