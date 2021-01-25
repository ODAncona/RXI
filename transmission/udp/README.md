---
description: User Datagram Protocol
---

# UDP

#### Fonctionnalités:

* **Adressage** d'application à l'aide de numéros de port
* **Contrôle d'erreur optionnel** \(checksum, obligatoire avec IPv6\)
* **Transmission non fiable**
  * Sans connexion
  * Sans acquittement ou retransmission
  * Sans contrôle de débit

#### Utilisation:

* Transmission multimédia \(stream tolère quelques pertes\)
* Transmission multicast \(multicast toujours sans connexion\)
* Les échanges courts, comme DNS \(sans connexion\)

{% hint style="info" %}
Le multicast intervient lors d'une transmission depuis un émetteur vers plusieurs récepteurs. Il utilise UDP pour éviter les complication liées à la retransmission et à la gestion de congestion à cause des récepteurs pluriels.
{% endhint %}

