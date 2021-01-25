---
description: Infrastructure de sécurité
---

# Firewall

Un Firewall empêche les dangers provenant de l'extérieur de se répandre à l'intérieur du réseau.

* Il restreint l'accès à un point précis
* Il empêche les agresseurs de s'approcher de vos autres défenses
* Il restreint la sortie à un point précis

![Le firewall prot&#xE8;ge le r&#xE9;seau local d&apos;un r&#xE9;seau externe](../../.gitbook/assets/image%20%28116%29.png)

## Fonctions

### Centre de décision de sécurité

* Goulet d'étranglement du trafic

### Impose le règlement de sécurité

* Sert à implémenter la politique de sécurité \(technique\)
* Restriction d'accès à des services dangereux sur internet

{% hint style="info" %}
La formation des utilisateurs sur les règles est tout autant importante pour la sécurité du réseau
{% endhint %}

### Surveillance du trafic depuis l'extérieur

* Permet de collecter des informations sur l'utilisation des services

### Limite d'exposition du réseau

* Un firewall interne peut confiner un problème de sécurité dans une partie du réseau

## Points faibles

Un firewall ne protège pas contre:

### Utilisateurs internes malveillant

* Si un attaquant se trouve déjà à l'intérieur du réseau, un firewall n'offre pas de protection

### Contre des connexions qui ne passent pas par lui

* Un point d'accès WLAN mal sécurisé peut permettre à un attaquant d'accéder au réseau sans passer par le firewall.

### Contre des virus / vers

* Un firewall réseau n'examine pas les données du niveau application.

{% hint style="info" %}
Pour ce faire il faut un ALG \(Application Layer Gateway\) ou un IDS \(Intrusion Detection System\)
{% endhint %}



## Architecture

Un firewall comprend généralement plusieurs éléments:

* Un ou plusieurs **filtres de paquets**
* Une ou plusieurs **passerelles applicatives**
* Un ou plusieurs **réseaux confinés**

la sécurité dépend de plusieurs éléments et l'agresseur doit franchir plusieurs barrières



