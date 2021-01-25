---
description: Conversion d'un nom de domaine en adresse IP
---

# Requête DNS

## Exemple

{% hint style="info" %}
Recherche du nom de domaine **www.cs.sjsu.edu** depuis la HEIG-VD
{% endhint %}

![](../.gitbook/assets/image%20%28134%29.png)

#### Déroulement

1. La requête type A est envoyée à un des serveurs DNS de la HEIG-VD
2. Le serveur DNS de la HEIG-VD ne connaît pas la réponse et envoie la requête à un des 13 serveurs racine
3. Recherche itérative: 
   * le serveur racine répond directement en indiquant le serveur DNS officiel de la zone .edu 
   * D’autres serveurs DNS sont capables d’effectuer des recherches récursives \(cherchent la réponse finale\)
4. Le serveur de la HEIG-VD continue avec la recherche récursive. Il contacte le serveur de la zone .edu 
5. Le serveur de la zone .EDU renvoie le serveur responsable de la zone sjsu.edu
6. Le server de la HEIG-VD continue la recherche récursive.
7. Le requête parvient au serveur officiel \(authoritative\) de la zone cs.sjsu.edu. Il connaît la réponse à la requête et la renvoie.
8. Retour de l'info jusqu'au destinataire final

## Cache DNS

Afin de réduire le trafic DNS, un serveur DNS peut garder une copie d’une réponse en cache

* Le paramètre «Durée de vie» \(TTL\) d’un enregistrement indique le temps qu’un serveur peut garder une réponse dans son cache
* Le serveur indique alors dans sa réponse qu’il s’agit d’une réponse non officielle

![Remplissage du cache lors d&apos;une requ&#xEA;te.](../.gitbook/assets/image%20%28102%29.png)

## DNS round-robin

Le système DNS de réaliser une méthode simple de répartition de charge

#### Méthode

* Un nom de domaine est associé avec plusieurs adresses IP
* Toutes ces machines réalisent le même service \(par exemple serveurs Web pour un site donné\)
* Le serveur DNS effectue une permutation des enregistrements à chaque requête DNS

![Le serveur DNS envoie une fois BAC et l&apos;autre CAB](../.gitbook/assets/image%20%28129%29.png)

