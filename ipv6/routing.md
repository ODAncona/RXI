---
description: Les différentes manières d'adresser avec IPv6
---

# Adressage IPv6

Une adresse IPv6 comporte 128 bits \(16 octets\)

* Adresses sur 128 bits \(16 octets\)
  * Selon des calculs très pessimistes, plus de 1000 adresses par m2 de la surface de la terre 
* Une interface a plusieurs adresses
  * Adresse locale de lien \(obligatoire\)
  * Adresse unicast globale \(optionnelle\)

### Adresse globale

Pour communiquer sur Internet, l’interface nécessite une adresse unicast globale \(=publique\)

#### Exemple: 

> **inet6 addr: 2001:0db8:0000:85a3:0000:0000:ac1f:8001 Scope:Global**

* Préfixe de routage alloué par l’ISP: 2001:123:12:: /48 
* Communication WAN
* Identificateur du sous-réseau: …1AA0… \(16 bits\)
* Identificateur de l’interface : ::1:2:3:4 \(64 bits\)

### Adresse Locale

#### Exemple

> **inet6 addr: fe80::20c:29ff::fe76:856b/64 Scope:Link**

* Préfixe FE80::/64
* Communication LAN
* Sans traverser de routeur

## Auto-configuration de l'identificateur de l'interface

L’ID de l’interface peut être construite automatiquement à partir de l’adresse MAC–Méthode EUI-64 modifiée

* Prendre l’adresse MAC d’une interface
* Ajouter FFFE au milieu
* Inverser le deuxième bit de poids faible du premier octet

![M&#xE9;thode EUI-64](../.gitbook/assets/image%20%28128%29.png)

{% hint style="danger" %}
La méthode EUI-64 permet d’identifier un utilisateur à distance via l’adresse IPv6
{% endhint %}

## Autres adresses

<table>
  <thead>
    <tr>
      <th style="text-align:left">Adresse</th>
      <th style="text-align:left">Explication</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">::1</td>
      <td style="text-align:left">
        <p><b>Adresse de rebouclage</b>
        </p>
        <p>(loopback) Similaire &#xE0; 127.0.0.1 en IPv4</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">::</td>
      <td style="text-align:left">
        <p><b>Adresse non sp&#xE9;cifi&#xE9;e</b> 
        </p>
        <p>Similaire &#xE0; 0.0.0.0 en IPv4.Utilis&#xE9;e si l&#x2019;adresse n&#x2019;est
          pas encore connue</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">FF00::/8</td>
      <td style="text-align:left">
        <p><b>Adresses multicast</b> 
        </p>
        <p>Par exemple FF02::1 &#x2192;tous les n&#x153;uds du &#x2018;lien&#x2019;
          (=LAN). L&#x2019;adresse FF02::1 correspond &#xE0; 255.255.255.255 en IPv4</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">FC00:/7</td>
      <td style="text-align:left">
        <p><b>Adresse locale unique </b>
        </p>
        <p>Similaire aux adresses priv&#xE9;es. Pour la communication&#xE0; l&#x2019;int&#xE9;rieure
          d&#x2019;une organisation (non routable sur Internet)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Comme unicast globale</td>
      <td style="text-align:left">
        <p><b>Adresse anycast</b>
        </p>
        <p>Une<b> </b>adresse globale peut &#xEA;tre assign&#xE9;e &#xE0; plusieurs
          interfaces/machines. Le routage normal fait qu&#x2019;un paquet avec une
          adresse anycastcomme destination est rout&#xE9; vers l&#x2019;interface
          la plus proche.</p>
      </td>
    </tr>
  </tbody>
</table>

#### **Anycast**

plusieurs serveurs peuvent avoir la même adresse anycast.



\*\*\*\*

