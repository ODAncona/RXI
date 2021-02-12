---
description: Wireless fidelity
---

# Introduction Wifi

#### Wi-fi

marque introduite par la Wi-Fi Alliance qui teste la compatibilité et fait la promotion de la technologie.

#### Avantages

* Mobilité
* Facilité et coût d'installation
* Toutes les plateformes \(smartphone, tablette\)

#### Inconvénients

* Débit faible partagé
* Problèmes liés à la transmission radio \(interférence, couverture\)
* Sécurité \(DoS, ...\)

## Normes principales

![Les diff&#xE9;rentes normes wifi](../.gitbook/assets/image%20%2890%29.png)

## Fréquences utilisées: micro-ondes

![Le spectre &#xE9;lectromagn&#xE9;tique](../.gitbook/assets/image%20%28115%29.png)

* Les fréquences radio sont comprises entre 250Mhz - 70 Ghz
* Les ondes se propagent en ligne droite

#### Fréquences &lt; 6Ghz

* Traverse facilement les murs

#### Fréquences &gt; 6Ghz

* Nécessite une visibilité directe

#### Fréquences &gt; 12Ghz

* Absorption par l'eau \( brouillard, pluie \)

## Bande de fréquence Wi-Fi

### Bande ISM \(Industrial/Scientific/Medical\)

* Bande 2.4 – 2.5 GHz
* Utilisation sans demande d’autorisation
* Utilisée par beaucoup d’équipements
* Interférences avec les fours micro-ondes \(2.45 GHz\)

### Bande U-NII \(Unlicensed National Information Infrastructure\)

* Bande 5.180 – 5.825 GHz
* Utilisation sans demande d’autorisation
* Peu utilisé, sauf pour 802.11 a/n/h

![Bande ISM et U-NII](../.gitbook/assets/image%20%2844%29.png)

## Choix d'un canal

* Chacune de ces bandes est divisée en canaux
* 802.11b/g/a utilisent un canal par cellule
* 802.11n utilise un ou deux canaux par cellule
* Le choix des bons canaux est important pour éviter de mauvaises performances

### 802.11b/g à 2.4 GHz

* 13 canaux en Europe 
  * Canal 14 uniquement au Japon
* Les canaux se **chevauchent**
  * Une transmission apparaît comme bruit dans les canaux voisins
  * Il est mieux de mettre deux réseaux dans le même canal que dans des canaux voisins
* Espacement recommandé de 5 canaux
  * Espacement des canaux: 5 MHz, largeur des canaux: 22 MHz
* Les canaux 1 – 6 – 11 sont les plus souvent utilisés

![Canaux utilisables](../.gitbook/assets/image%20%28100%29.png)

## Exemple d'une transmission

![Transmission Wi-Fi A -&amp;gt; AP -&amp;gt; B](../.gitbook/assets/image%20%2865%29.png)

* Chaque trajet est acquitté
* Puisque SIFS &lt; DIFS, l’acquittement est transmis avec priorité
* Le point d’accès n’a pas de priorité \(Il est possible qu’une autre station gagne accès au canal avant lui\) 

## Evitement de collision

Défaut de CSMA simple : Lorsque plusieurs émetteurs attendent la libération du canal, il y aura forcement une collision

### CSMA/CA \(Collision Avoidance\)

#### Principe

une station doit attendre un délai aléatoire :

1. Si le canal est occupé lors de l’écoute \(=&gt; CSMA non persistant\) 
2. Après une transmission réussie
3. Après chaque retransmission \(=après une collision ou une erreur de bit\)

#### Résultat

* Evite les collisions quand le canal se libère
* Empêche une station de monopoliser le canal
* Toutes les stations ont la même priorité d’accéder au canal
* Pas de Qualité de Service \(délais peuvent être longs\)

#### Exemple

![](../.gitbook/assets/image%20%2883%29.png)

## Débit effectif

Les normes indiquent le débit physique de transmission de bits

* Par exemple 54 Mb/s pour 802.11g

Le débit effectif est inférieur à cause

* des en-têtes des trames
* des délais d’attente \(DIFS, délais aléatoires, acquittements\)

