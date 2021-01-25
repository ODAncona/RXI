---
description: Mesurer les délais lors de l'acheminement de paquet
---

# Performance

Il y a plusieurs indicateurs pour mesurer la performance d'un réseaux

* délai _\[s\]_
* vitesse de propagation _\[m/s\]_
* longueur des données _\[bits\]_
* débit binaire _\[bits/s\]_
* taux de perte _\[%\]_

## Délai de transit

le délai de transit est le temps total entre l’émission du premier bit par la source et la réception du dernier bit par le récepteur final. Il est composé de:

* Délai de transmission
* Délai de propagation
* Délai de traitement
* Délai d'attente

$$
t_{transit}=t_{transmission}+t_{propagation}+t_{attente+propagation}
$$

## Délai de transmission

![](../.gitbook/assets/image%20%2855%29.png)

Définition: Délai pour mettre les bits sur le médium

$$
t_{transmission}[s] = \frac{tailleDuPaquet[bits]}{débit[bits/s]}
$$

## Délai de propagation

![](../.gitbook/assets/image%20%2822%29.png)

Définition: Délai du signal physique entre émetteur et récepteur



$$
t_{propagation}[s] = \frac{distance[m]}{vitesseDePropagation[m/s]}
$$

## Délai de traitement + Délai d'attente

![](../.gitbook/assets/image%20%28122%29.png)

Délai de traitement: Délai de calcul nécessaire à un nœud 

* Vérification de la somme de contrôle
* Recherche dans la table de routage

Délai d'attente: Délai d’attente dans la file d’attente de l’interface sortie

$$
t_{attente}[s]=\sum \frac{Nombre De PaquetsDansLaFile[bit]}{Débit[bit/s]}
$$

![](../.gitbook/assets/image%20%2821%29.png)

