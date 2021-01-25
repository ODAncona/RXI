---
description: Méthode de concurrence pour utiliser le médium physique
---

# Medium Partagé

Initialement, Ethernet a été conçu comme bus, donc avec un médium partagé. ça signifie:

* Une seule transmission ****est possible à chaque instant
* Si deux stations transmettent au même moment, une collision se produit
* La collision rend les bits illisibles pour les récepteurs

Lors de l’utilisation d’un médium partagé, une méthode est nécessaire pour décider qui peut transmettre afin de minimiser les collisions.

## CSMA

Sur un médium partagé, Ethernet utilise un protocole de type CSMA : Carrier Sense – Multiple Access

* Carrier Sense : écouter si le canal est libre avant de transmettre
* Multiple Access : partage du même canal de transmission

![](../.gitbook/assets/image%20%2879%29.png)



