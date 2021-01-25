---
description: Les logiciels de réseaux sont organisés avec une pile de couches
---

# Communication en Couche

Les logiciels de réseaux sont organisés en une pile de couches Chaque couche offre un service bien défini :

* Abstraction de la complexité du système
* Permet l’interconnexion de réseaux hétérogènes

![Base du mod&#xE8;le en couche](../.gitbook/assets/image%20%2875%29.png)

#### Entité paires

Entités du même niveau, qui communiquent entre elles – Processus informatique qui tourne sur les deux machines

#### Protocole

Règles et conventions qui régissent la communication entre pairs

#### Communication horizontale

![Communication horizontale](../.gitbook/assets/image%20%2858%29.png)

Le but de la communication est de transmettre les données entre homologues \(pairs\) en utilisant un protocole de communication

#### Communication verticale

![Communication verticale](../.gitbook/assets/image%20%284%29.png)

* Le chemin réel emprunté par les données traverse les différentes couches
* Chaque couche réalise un service bien défini
* L’entité de chaque couche utilise un protocole pour communiquer avec son pair
* Le support physique véhicule finalement les données

#### Encapsulation

![](../.gitbook/assets/image%20%28117%29.png)

* Chaque protocole peut ajouter un en-tête \(et un en-queue\)
* Par exemple somme de contrôle
* Ces informations sont utilisées par son pair
* Elles sont enlevées avant de passer les données à la couche supérieur

#### Adressage

* Les en-têtes contiennent aussi des adresses
* Une adresse indique l’entité de la couche supérieure à qui il faut passer les données
* Par exemple serveur Web ou serveur Mail
* Par exemple protocole TCP UDP

### Terminaux & systèmes intermédiaires

![interm&#xE9;diaires entre deux ordinateurs](../.gitbook/assets/image%20%2842%29.png)

La communication entre nœuds terminaux traverse souvent des nœuds intermédiaires:

* routeurs
* switch
* access point

Ces nœuds n'implémentent pas toutes les couches. De plus, les protocoles peuvent être différents entre les liens \(wifi, puis ethernet\)

