---
description: Un firewall est composés de plusieurs types d'équipements
---

# Types d'équipements

## Routeur écran

{% hint style="info" %}
Aussi appelé: **Routeur écran** ou **firewall réseau**
{% endhint %}

### 

![](../../.gitbook/assets/image%20%28133%29.png)

### Filtrage de paquet

* Achemine de manière sélective les paquets entre internet et le réseau local

Filtre les paquets entrants et sortants selon

* Les informations des en-têtes IP et TCP \(IP src, IP dest, port src, port dest, protocole...\)
* les informations de routage \( interface d'entrée, interface de sortie\)

### Configuration

Sur linux on utilise **iptables**

Configuration comme firewall chaîne FORWARD

#### Refus par défaut

```text
iptables -F     
iptables -P INPUT DROP  
iptables -P OUTPUT FORWARD
iptables -P FORWARD DROP 
```

Ouvrir SSH sur le serveur 10.1.1.1

```text
iptables -t filter -A FORWARD -d 10.1.1.1 -p tcp -dport 22 -j ACCEPT
iptables -t filter -A FORWARD -s 10.1.1.1 -p tcp -sport 22 -j ACCEPT   
```

## Passerelle applicative

{% hint style="info" %}
Aussi appelé: **Serveur mandataire** ou **Proxy**
{% endhint %}

* Sécurise les communications des utilisateurs
* Accepte les requêtes des clients et les redirige vers le vrai serveur
* Respecte la politique de sécurité de l'entreprise
* Transparent pour les utilisateurs
* Doit être complété par un mécanisme qui restreint les communications directes

