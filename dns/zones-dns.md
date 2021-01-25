---
description: Hiérarchie de responsabilité
---

# Zones DNS

DNS est un système hiérarchique et distribués de serveurs

L’espace des noms DNS est divisé en **zones** distinctes:

* Une zone est une partie de l’arborescence pour laquelle la responsabilité administrative a été déléguée
* Typiquement une zone dispose d’un serveur DNS primaire et plusieurs serveurs secondaires
* Une zone peut créer des sous-zones en déléguant l’autorité à d’autres serveurs DNS subordonnés
* Le serveur officiel \(authoritative server\) est celui qui est responsable pour une zone et qui n’a pas délégué la responsabilité

### Exemples

* La racine délègue la responsabilité pour la zone .edu
* La zone .edu délègue la responsabilité pour yale.edu
* La zone yale.edu gère le serveur officiel pour eng.yale.edu
* Elle délègue la responsabilité pour cs.yale.edu à un autre serveur

![](../.gitbook/assets/image%20%283%29.png)

