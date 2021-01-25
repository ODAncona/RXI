---
description: DNS a une longue histoire de vulnérabilités et de failles...
---

# Sécurité

## DNS cache poisoning

1. Un attaquant demande à un serveur DNS victime l’adresse IP de www.wikipedia.org
2. Le serveur DNS effectue une requête récursive et demande au serveur DNS de la zone wikipedia.org
3. L’attaquant envoie une réponse DNS au serveur DNS victime avec une fausse adresse IP  
4. Le serveur victime met l’adresse fausse dans son cache et la distribue lors de requêtes légitimes

![](../.gitbook/assets/image%20%2833%29.png)

Difficile à réaliser, mais possible:

* Les requêtes/ réponses DNS incluent un numéro que l’attaquant doit deviner
* Les serveurs DNS utilisent maintenant des ports sources randomisés qu’il faut également deviner

## DNSSEC

DNSSEC vise à sécuriser DNS

* Les réponses DNS sont signées cryptographiquement, mais pas chiffrées
  * Signature avec la clé privée du serveur DNS
  * Une réponse DNS contient un nouvel enregistrement RRSIG avec la signature de l’enregistrement principal de la réponse
* Un client peut obtenir la clé publique du serveur en demandant l’enregistrement du type DNSKEY pour ce serveur DNS
* Les clés d’une zone doivent être signées par la zone supérieure
  * Ceci crée une chaîne de confiance depuis la racine DNS 
* Actuellement les serveurs racine et une partie des noms de domaine de premier niveau implémentent DNSSEC

