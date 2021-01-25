---
description: Gestion des adresses IP par l'IANA et pénurie des adresses IPv4b dans le monde
---

# Allocation des adresses IP

## Gestion des adresses IP

L'IANA est une organisation qui standardise et distribue les adresse IP ainsi que les ports. Elle divise le monde en plusieurs groupes:

| Nom | Description |
| :--- | :--- |
| **R.I.R.** | Regional Internet Registry |
| **N.I.R.** | National Internet Registry |
| **L.I.R.** | Local Internet Registry |
| **I.S.P.** | Internet Service Provider |
| **E.U.** | End User |

* IANA alloue des blocs d’adresses aux Registres Régionaux d’Adresses IP \(RIR\)
* RIPE NCC est responsable pour l’Europe. Il reçoit les blocs d’adresses d’IANA
* RIPE NCC alloue des blocs d’adresses aux Registres Internet Locaux LIR qui sont typiquement des opérateurs comme Swisscom
* Les opérateurs allouent les adresses à leurs clients ou d’autres organisations

![](../.gitbook/assets/image%20%2898%29.png)

![R&#xE9;partition g&#xE9;ographique des RIR](../.gitbook/assets/image%20%2828%29.png)

## Allocation des préfixes de routage

#### Politique d’allocation typique

* IANA donne aux RIRs des blocs de /12 à /23
* Les RIRs donnent aux LIRs des blocs de /19 à /32
* Les LIRs donnent aux clients des blocs de /48 à /56
* L’utilisateur dispose de 8 – 16 bits pour créer des sous-réseaux s’il veut

Actuellement, uniquement les préfixes 2000::/3 sont alloués:

* Préfixes 2000:: -3FFF::de toutes les adresses globales utilisables actuellement
* Un huitième de l’espace d’adressage total

## Disponibilités des adresses IPv4

* IANA a alloué les derniers blocs /8 aux RIR en février 2011
* RIPE NCC a alloué le dernier bloc /8 en septembre 2012
  * Il dispose encore d’un demi-bloc /8 qui permet de distribuer 8’000 blocs de /22 \(1024 adresses par bloc\) aux LIR
* Les LIR ont encorequelques réserves d’adresses IPv4

![](../.gitbook/assets/image%20%28114%29.png)

