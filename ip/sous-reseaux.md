---
description: Comment partitionner une plage d'adresse IP en plusieurs sous réseaux
---

# Sous réseaux

Les adresses de classe fixe \(A,B,C,D\) sont rigides et imposent soit un gaspillage d'adresse soit une gestion difficile des sous réseaux.

#### Idée

Subdiviser une plage d’adresse en plages plus petites et les allouer à différents réseaux physiques

![R&#xE9;seau d&apos;entreprise scind&#xE9; en plusieurs sous r&#xE9;seaux](../.gitbook/assets/image%20%2839%29.png)

## Masque de sous réseau

Le masque de sous réseau permet de diviser une plage d’adresses en sous-réseaux. Il est constitué de 1 pour la partie réseau et de 0 pour la partie hôte.

![Exemple d&apos;un sous r&#xE9;seau avec une adresse de classe B](../.gitbook/assets/image%20%28120%29.png)

Plus il y a de 1 dans le masque, plus il y aura de sous réseau disponibles et moins d'hôtes adressables. Ici, il y a $$2^6 = 64$$sous réseaux et $$2^{10} =1024 $$stations. 

{% hint style="danger" %}
Seulement $$2^{n}-2$$stations sont effectivement adressable ! Car il y a l'adresse broadcast et de réseau qui ne sont pas allouables.
{% endhint %}

### Déterminer un masque de sous-réseaux:

Nous devons déterminer le masque de sous réseaux avec:

* Type de réseau \(A,B,C,D\)
* n = nombre de sous réseaux
* x = nombre de machines

1. Déterminer le nombre d'octet rempli de 1 en fonction de la classe d'adresse
2. Mettre à 1 le nombre de bit nécessaire pour adresser n sous réseaux $$2^{nombreDeBits} \ge n$$
3. Vérifier si il y reste suffisamment de bits pour adresser x machines et décider d'attribuer les bits restants pour plus de sous réseaux ou de machines.

![Exemple avec Classe = B, n = 10, x = 600](../.gitbook/assets/image%20%2820%29.png)

### Déterminer les adresses d’un sous-réseau:

Le but est de connaître toutes les adresses d'un sous-réseau en connaissant:

* x = adresse ip
* m = masque de sous réseau

1. Commencer par identifier la classe d'adresse \(le nombre d'octet rempli de 1\) et repérer l'octet déterminant les sous réseaux dans le masque
2. Convertir l'octet concerné en binaire afin de le superposer avec le masque. Là ou il y a des 1 sur le masque, il y a le préfixe réseau dans l'adresse ip.
3. La plage d'adresse: 
   1. commence au **préfixe** **réseau + 0** \(adresse réseau\) 
   2. se termine au **préfixe réseau + 1** \(adresse broadcast\)

![Exemple avec x = 200.23.15.147 et m = 255.255.255.224](../.gitbook/assets/image%20%2878%29.png)

### Notation CIDR

C'est une nouvelle notation permettant de réduire la taille des tables de routage en indiquant le nombre de bits à 1 avec un slash.

Exemple: 200.123.230.13**/21**

| Type | Decimale | Binaire |
| :--- | :--- | :--- |
| ip | 200.123.230.13 | 11001000**.**1111011**.**11100110**.**00001101 |
| masque |  255.255.248.0 | 11111111**.**1111111**.**11111000**.**00000000 |

Indique un masque avec les premiers 21 bits à 1 ce qui correspond à un masque de 255.255.248.0. Le préfixe réseau est donc 11100.



