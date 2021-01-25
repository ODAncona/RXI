---
description: Evolution dynamique de la topologie du réseau
---

# Routage Dynamique

Trouver « le meilleur chemin » vers chaque destinataire selon le nombre de sauts, la capacité des liens, le délai, le trafic ou la disponibilité...

Nécessite un protocole de routage sur le routeur qui:

* communique avec les autres routeurs
* remplit la table de routage du routeur
* S’adapte aux changements \(panne d’un lien, nouveau lien\)

Il existe deux famille de protocole de routage:

* État de lien
* Vecteur de distance

## État de lien

* Un routeur apprend **la topologie complète** du réseau
* Famille de protocoles qui vise à corriger les problème des méthodes par vecteur de distance.
* Chaque routeur effectue périodiquement plusieurs opérations. 

#### Principe 

* Découvrir ses voisins et apprendre leurs adresses respectives
* Déterminer la distance vers chacun des voisins
* Construire un paquet contentant l’information apprise
* Envoyer ce paquet spécial à tous les autres routeurs du sous-réseau
* Calculer le plus court chemin vers tous les autres routeurs

### Envoi des états de lien aux voisins

Chaque routeur construit des paquets contentant l’information sur l’état des liens locaux 

\(**LSP**: link state packet\)

![Tous les liens de chaque n&#x153;uds sont stock&#xE9;s dans un LSP](../../.gitbook/assets/image%20%2896%29.png)

Les LSP d’un routeur sont diffusés dans le réseau entier. 

#### Inondation fiable

* Un routeur transmet un LSP reçu sur tous les ports
* Un numéro de séquence permet d’éliminer des LSP dupliqués
* Les autres routeurs enregistrent le LSP le plus récent de chaque autre routeur
* Éliminer les LSP quand sa durée de vie est terminée
* La réception d’un LSP est confirmé par un accusé de réception

## Vecteur de distance

C'est un type de protocole permettant de construire des tables de routages où aucun routeur ne possède la vision globale du réseau.

### Exemples

* RIP
* IGRP
* EIGRP

## Comparaison

| Caractéristiques | Vecteur de distance | État de lien |
| :--- | :--- | :--- |
| Information envoyée | état du réseau **global**, vu par le routeur | état des liens **locaux**, vus par le routeur |
| Destinataire de l'information | Uniquement les voisins directs | Tous les nœuds du réseau, par inondation |
| Méthode de calcul | Bellman-Ford **calcul partiel** pour compléter le calcul effectué par les voisins | Dijkstra **calcul complet** sur la base des informations reçues de tous les autres nœuds |
| Avantages | Protocole simple | Convergence rapide et fiable |
| Inconvénients | Convergence peut être lente Vecteurs de distance peuvent être volumineux | Envoi des message par inondation est complexe |

