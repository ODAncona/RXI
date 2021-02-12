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

![Les diff&#xE9;rentes normes wifi](../.gitbook/assets/image%20%28115%29.png)

## Fréquences utilisées: micro-ondes

![Le spectre &#xE9;lectromagn&#xE9;tique](../.gitbook/assets/image%20%28139%29.png)

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

![Canaux utilisables](../.gitbook/assets/image%20%28138%29.png)

### 802.11n à 2.4 GHz

* Utilisation avec 1 canal est similaire à 802.11b/g
* Utilisation avec deux canaux double la largeur de bande et le débit nominal
  * Les deux canaux doivent être séparés de 20 MHz
  * Par exemple canaux 1+5 ou 6+10
  * Un seul réseau 802.11n @2.4 GHz bloque 9 des 13 canaux

![](../.gitbook/assets/image%20%2866%29.png)

### 802.11a et 802.11n à 5 GHz

* En Europe, 19 canaux sans interférences mutuelles
* Largeur de bande de 20 MHz par canal
* 802.11n peut utiliser un ou deux canaux

![](../.gitbook/assets/image%20%28141%29.png)

## Accès au médium

* Le canal radio est partagé entre tous les émetteurs • Contrairement à un bus sur câble coaxial, la détection de collisions est difficile
* CSMA/CD d’Ethernet n’est pas utilisable

#### Principe de csma dans 802.11

1. Un émetteur écoute le canal avant de transmettre
2. Si le canal est libre pendant l’intervalle DIFS: transmission
3. Si le canal est occupé: attendre un délai aléatoire

   ➔ CSMA non persistant, contrairement à Ethernet

4. Chaque trame doit être acquittée après chaque transmission

   • Intervalle SIFS \(&lt; DIFS\) entre la réception de la trame et l’acquittement

### Exemple d'une transmission

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

![](../.gitbook/assets/image%20%28100%29.png)

### Faiblesse de CSMA/CA

Collisions toujours possibles:

* Les délais aléatoires de deux stations expirent simultanément
* Problème de la station cachée

![station cach&#xE9;e](../.gitbook/assets/image%20%2890%29.png)

Mode RTS/CTS avec réservation du canal

* Evite le problème de la station cachée
* Réduit la durée d’une collision

### Réservation avec RTS et CTS

Message RTS \(Request to Send\)

* Court message envoyé par la source pour indiquer l’intention d’émettre 

Message CTS \(Clear to Send\)

* Court message envoyé par la destination comme réponse au message RTS
* Reçu par tous les nœuds dans la zone de couverture du point d’accès
* Indique la durée de la réservation \(NAV, Network Allocation Vector\)

Comportement

* Réception d’un RTS: silence pendant la transmission de CTS + réservation
* Réception de CTS: silence pendant la transmission suivante

![](../.gitbook/assets/image%20%28140%29.png)

## Débit effectif

Les normes indiquent le débit physique de transmission de bits

* Par exemple 54 Mb/s pour 802.11g

Le débit effectif est inférieur à cause

* des en-têtes des trames
* des délais d’attente \(DIFS, délais aléatoires, acquittements\)

| Norme | Débit maximum de la couche physique | Débit effectif \(paquet de 64B\) | Débit effectif \(paquet de 1500B\) |
| :--- | :--- | :--- | :--- |
| 802.11b | 11 Mb/s | 0.8 Mb/s | 7.1 Mb/s |
| 802.11g/a | 54 Mb7s | 1.3 Mb/s | 20 Mb/s |

### 

