---
description: Comment acheminer un paquet sur internet
---

# Adressage IP

## Routeur

Un routeur est un équipement de la couche 3 qui permet d’interconnecter plusieurs réseaux ou de les séparer.

Chaque réseau doit avoir sa propre plage d’adresse:

* Tous les équipements du réseau ont une adresse de cette plage
* Les différentes interfaces d’un routeur font partie de réseaux différents

## Adressage IP

### Définition

Le protocole IP est un composant essentiel d'internet. Chaque interface réseau connectée à Internet doit avoir une adresse IP pour être atteignable et s'échanger des données. Un PC peut avoir plusieurs adresses IP. Certaines adresses ont une signification particulière:

* Adresse locale
* Adresse broadcast

### Structure

Longueur: 4 octets en notation pointée \(192.168.1.1\)

Elle contient deux parties:

* Identificateur de réseau \(Network ID\): Assigné par une autorité \(par exemple ISP\)
* Identificateur de machine \(Host ID\): Assigné par l’entreprise, l’organisation ou l’utilisateur

![Selon les besoin, on aura plus ou moins de r&#xE9;seaux ou de machines](../.gitbook/assets/image%20%2864%29.png)

### Classe d'adresses

Selon la longueur du préfixe réseau, on distingue plusieurs classes d’adresses. A chaque fois, le masque de sous réseaux sera multiple d'un octet\( A = 8, B = 16, C = 24\).

![Les premiers bits d&#xE9;finissent de quelle classe sera l&apos;adresse IP](../.gitbook/assets/image%20%28123%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Classe</th>
      <th style="text-align:left">Pr&#xE9;fixe r&#xE9;seau</th>
      <th style="text-align:left">Suffixe machine</th>
      <th style="text-align:left">Plage d&apos;adresses</th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">A</td>
      <td style="text-align:left">8 bits</td>
      <td style="text-align:left">24 bits</td>
      <td style="text-align:left">1.0.0.0 - 127.255.255.255</td>
      <td style="text-align:left">
        <ul>
          <li>126 r&#xE9;seaux</li>
          <li>16M H&#xF4;tes</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">B</td>
      <td style="text-align:left">16 bits</td>
      <td style="text-align:left">16 bits</td>
      <td style="text-align:left">128.0.0.0 - 191.255.255.255</td>
      <td style="text-align:left">
        <ul>
          <li>16k r&#xE9;seaux</li>
          <li>64k H&#xF4;tes</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">C</td>
      <td style="text-align:left">24 bits</td>
      <td style="text-align:left">8 bits</td>
      <td style="text-align:left">192.0.0.0 - 255.255.255.255</td>
      <td style="text-align:left">
        <ul>
          <li>2M r&#xE9;seaux</li>
          <li>254 H&#xF4;tes</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">D</td>
      <td style="text-align:left">-</td>
      <td style="text-align:left">-</td>
      <td style="text-align:left">224.0.0.0 - 239.255.255.255</td>
      <td style="text-align:left">Adresse multicast: &quot;tous les routeurs&quot;</td>
    </tr>
  </tbody>
</table>

### Adresses particulières

| Type | Adresse | Commentaire |
| :--- | :--- | :--- |
| Loopback | 127.x.y.z  | Typiquement 127.0.0.1. Utilisé pour des tests et pour la communication entre processus de la même machine. |
| Broadcast local | 255.255.255.255 | Broadcast à l’intérieur d’un réseau |
| Adresse du réseau | Préfixe réseau + tous les autres bits à 0 | Première adresse du réseau. Ne peut pas être assignée à une machine. |
| Adresse broadcast d’un réseau | Préfixe réseau + tous les autres bits à 1 | Dernière adresse du réseau. Broadcast depuis l’extérieur. Ne peut pas être assignée à une machine. |

On ne peut donc pas assigner l'adresse broadcast et l'adresse du réseau.



