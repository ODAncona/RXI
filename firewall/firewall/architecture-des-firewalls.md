---
description: Différents types d'architecture
---

# Architecture des firewalls

## Routeur écran simple

* Architecture simple avec un seul niveau de protection
* Utilisé par exemple dans les réseaux à domicile

![](../../.gitbook/assets/image%20%2849%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Avantages</th>
      <th style="text-align:left">Inconv&#xE9;nients</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>Simple &#xE0; mettre en place</li>
          <li>Niveau de s&#xE9;curit&#xE9; basique</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Une seule ligne de d&#xE9;fense</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## Hôte à double réseau

* L’hôte à double réseau est connecté aux réseaux interne et externe
* Le routage est désactivé
* Connexion avec l’extérieur \( les utilisateurs peuvent se loguer sur l'hôte afin d'utiliser internet\)
* Applicable si peu de connexions avec l’extérieur

![](../../.gitbook/assets/image%20%28124%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Avantages</th>
      <th style="text-align:left">Inconv&#xE9;nients</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>Bon niveau de s&#xE9;curit&#xE9;</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Solution peu commode pour les utilisateurs</li>
          <li>Gestion des comptes vuln&#xE9;rable</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## Routeur écran avec bastion

Machine **bastion** exposé à internet ****située sur le réseau interne

#### Bastion

* Peut recevoir des connexions depuis l’extérieur
* Peut travailler comme proxy pour les connexions depuis l’intérieur
* Le routeur écran ne permet que les connexions depuis / vers le bastion

![](../../.gitbook/assets/image%20%2841%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Avantages</th>
      <th style="text-align:left">Inconv&#xE9;nients</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>Bon niveau de s&#xE9;curit&#xE9;</li>
          <li>Plus commode pour les utilisateurs</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Le bastion se trouve sur le r&#xE9;seau interne</li>
          <li>Le routeur &#xE9;cran est l&#x2019;unique point de d&#xE9;fense</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## Sous-réseau à écran \(DMZ\)

Couche de sécurité supplémentaire

#### DMZ \(demilitarized zone\)

* Isole le bastion, qui est vulnérable aux attaques
* Un intrus ayant réussi à s’infiltrer sur le bastion doit encore franchir le routeur écran intérieur
* Le trafic LAN ne peut pas être espionné depuis le bastion

![](../../.gitbook/assets/image%20%285%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Avantages</th>
      <th style="text-align:left">Inconv&#xE9;nients</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>Solution tr&#xE8;s s&#xE9;curis&#xE9;e</li>
          <li>Solution standard dans les r&#xE9;seaux d&apos;entreprise</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Solution couteuse</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## Variante: Plusieurs bastions

Séparation des bastions, par exemple:

* Bastions pour les utilisateurs internes \(proxy, e-mail\) plus serveurs accessibles depuis Internet
* Isolation des services vulnérables \(FTP\) sur une machine séparée

![](../../.gitbook/assets/image%20%28126%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Avantages</th>
      <th style="text-align:left">Inconv&#xE9;nients</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>Performances am&#xE9;lior&#xE9;es</li>
          <li>Diff&#xE9;rents niveaux de s&#xE9;curit&#xE9;</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Solution couteuse</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## Variante: Fusion des routeurs externe et/interne

Le bastion reste isolé sur le réseau périphérique.\(gestion des services critique\). Le routeur peut autoriser le passage directe de certains services.

![](../../.gitbook/assets/image%20%2899%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Avantages</th>
      <th style="text-align:left">Inconv&#xE9;nient</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>Ne diminue que peu la s&#xE9;curit&#xE9;</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Le routeur est le seul &#xE9;l&#xE9;ment de d&#xE9;fense</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## Variante: Fusion du routeur externe et du bastion

* Architecture pratique pour les petits sites
* Connexion ADSL
* Machine à l’entrée fonctionne comme routeur écran plus bastion
* Diminue peu la sécurité

![](../../.gitbook/assets/image%20%28109%29.png)

## Configuration dangereuse

{% hint style="danger" %}
NE PAS fusionner bastion et routeur interne
{% endhint %}

Rend inutile le réseau périphérique:

* Si le bastion est infiltré, l’agresseur a accès au trafic LAN
* Résulte en une architecture hôte à écran

![Configuration vuln&#xE9;rable](../../.gitbook/assets/image%20%2856%29.png)

