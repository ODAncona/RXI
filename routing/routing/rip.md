---
description: Routing Information Protocol
---

# RIP

* Chaque routeur maintient une table de routage qui indique les distances vers les réseaux destinataires
* Chaque routeur envoie périodiquement sa table de routage \(« vecteur de distances »\) à tous ses voisins
* Chaque routeur utilise les tables de routage reçues pour calculer ses routes
* Pour éviter les boucles de routage, le nombre de sauts est limité à 15. Au-delà, les paquets sont supprimés

#### Algorithme de Bellman-Ford distribué

Pour calculer la meilleure route vers un réseau X 

1. Le routeur choisit la route la plus courte vers X parmi celles annoncées par les voisins
2. Il incrémente la distance de la route de 1 pour tenir compte de la distance entre lui et le voisin

### Propagation des bonnes nouvelles

Une meilleure route se propage **rapidement**

![La nombre de sauts est indiqu&#xE9; apr&#xE8;s le d&#xE9;marrage de A](../../.gitbook/assets/image%20%2814%29.png)

### Propagation de mauvaises nouvelles

Après une panne, le routage converge **très lentement**

![La liaison A-B vient de tomber](../../.gitbook/assets/image%20%288%29.png)

## Heuristiques pour accélérer la convergence

### Distance Maximale

* Une distance au-delà de n est infinie
* Limite la taille maximale d’un réseau

### Horizon éclaté \(Split horizon\)

* La distance vers une destination n’est pas annoncée au nœud suivant dans cette direction

![La coupure de C-D pose probl&#xE8;me car A-B peuvent communiquer](../../.gitbook/assets/image%20%2893%29.png)

### Horizon éclaté avec retour empoisonné

Un routeur avise ses voisins qu’une route est devenue impraticable avec une distance infinie



