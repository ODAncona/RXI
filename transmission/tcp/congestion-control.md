---
description: l’émetteur adapte le débit en fonction du réseau
---

# Contrôle de congestion

#### Le contrôle de congestion:

* Adaptation à la vitesse du réseau
* Évitement des pertes excessives de paquets à cause d'une surcharge du réseau

#### État de congestion

* Le réseau n’est plus en mesure de transporter tout le trafic injecté et perd des paquets

{% hint style="warning" %}
Danger de l’amplification d’une congestion par TCP par une retransmission excessive de la perte de paquets
{% endhint %}

{% hint style="success" %}
Le contrôle de congestion de TCP doit optimiser le débit de transmission sans mettre en danger la stabilité du réseau
{% endhint %}

## Bases du contrôle de congestion de TCP

<table>
  <thead>
    <tr>
      <th style="text-align:left">Nom</th>
      <th style="text-align:left">Acronyme</th>
      <th style="text-align:left">D&#xE9;finition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Maximum Segment Size</td>
      <td style="text-align:left">mss</td>
      <td style="text-align:left">
        <ul>
          <li>Taille maximum d&#x2019;un paquet</li>
          <li>Cwnd double chaque RTT (d&#xE9;lai aller-retour)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Slow Start Threshold</td>
      <td style="text-align:left">ssthresh</td>
      <td style="text-align:left">
        <ul>
          <li>taille maximum d&apos;une fen&#xEA;tre d&apos;&#xE9;mission en slow start</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">advertised Window</td>
      <td style="text-align:left">awnd</td>
      <td style="text-align:left">
        <ul>
          <li>fen&#xEA;tre de r&#xE9;ception</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Congestion Window</td>
      <td style="text-align:left">cwnd</td>
      <td style="text-align:left">
        <ul>
          <li>G&#xE9;r&#xE9;e par l&apos;&#xE9;metteur pour limiter le d&#xE9;bit d&apos;&#xE9;mission</li>
          <li>TCP adapte sa taille au niveau de congestion d&#xE9;tect&#xE9;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Sending Window</td>
      <td style="text-align:left">swnd</td>
      <td style="text-align:left">
        <ul>
          <li>fen&#xEA;tre d&apos;&#xE9;mission (= min (cwnd, awnd))</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">retransmit timeout</td>
      <td style="text-align:left">rto</td>
      <td style="text-align:left">
        <ul>
          <li>temps de transmission maximal (souvent 2 fois le RTT)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Roundtrip time</td>
      <td style="text-align:left">rtt</td>
      <td style="text-align:left">
        <ul>
          <li>Dur&#xE9;e d&apos;envoi puis de r&#xE9;ception d&apos;acquittement d&apos;un
            paquet</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### Combinaison du contrôle de flux et de congestion

La taille de la fenêtre est proportionnelle au débit, donc la fenêtre régule le débit

### Principe

L’émetteur adapte valeur cwnd en fonction des acquittements reçus ou des pertes détectées

Il y a trois phases, avec des règles différentes pour adapter cwnd:

* **Démarrage lent:** Pour détecter le débit optimal, TCP commence avec une petite fenêtre de congestion et augmente rapidement le débit
* **Évitement de congestion:** Dès que TCP s’approche de la zone de congestion, TCP augment le débit plus lentement
* **Accroissement additif - décroissance multiplicative:** Dès qu’une perte est détectée TCP ralentit rapidement puis augmente à nouveau lentement

## Slow Start

* TCP doit fonctionner correctement pour n’importe quelle capacité du réseau \(entre bits/s et Gb/s\)
* Il faut éviter de surcharger un lien lent au départ➢Petite fenêtre cwnd au début
* Il faut rapidement arriver à exploiter la capacité de liens importants➢Augmentation rapide de cwnd

### Algorithme Slow Start

* initialement cwnd = 1MSS
* Ensuite cwnd est incrémenté de 1MSS par acquittement reçu

{% hint style="info" %}
La fenêtre de congestion cwnd double à chaque RTT \(délai aller-retour\)
{% endhint %}

![](../../.gitbook/assets/image%20%2872%29.png)

## Congestion avoidance

* Dans Slow Start, la taille de cwnd augmente exponentiellement
* Augmentation doit ralentir quand TCP s’approche du ‘débit optimal’
* Un seuil d’évitement de congestion indique quand on s’approche d’une congestion \(ssthresh\)

### Algorithme Slow Start

* Dès que $$cwnd > ssthresh$$ , cwnd est agrandi linéairement
* Pour chaque acquittement reçu $$cwnd \mathrel{{+}{=}} \dfrac{MSS \times MSS}{cwnd}$$ 

{% hint style="info" %}
Au-dessus du seuil la fenêtre de congestion croît d'un MSS chaque RTT
{% endhint %}

### Exemple

![](../../.gitbook/assets/image%20%2843%29.png)

## Variation du seuil d’évitement de congestion

Comment déterminer la valeur du seuil de congestion ssthresh?

1. Lorsqu’il n’y a pas de congestion, ssthresh croît linéairement avec cwnd → **accroissement additif**
2. Lorsqu’une perte a été détectée, ssthresh est diminué à la moitié → **décroissance multiplicative**

Théorie des files d’attente : _Pour garantir la stabilité du réseau, le débit doit diminuer de manière exponentielle_

TCP \(reno\) recommence avec Slow Start pour éviter des rafales de retransmissions

### Comportement de cwnd et sstresh

#### Trois phases

* **Slow Start** avec une croissance exponentielle de cwnd
* Congestion avoidance \(**accroissement additif de sstresh**\)
* Diminution de sstresh lors d'une perte \(**décroissance multiplicative de sstresh**\)

![](../../.gitbook/assets/image%20%28136%29.png)

## Fast Recovery

L’utilisation de Slow Start après des pertes isolées n’est pas optimale

* Si des segments intermédiaires ont été perdus mais les segments suivants sont arrivés, cela indique une congestion légère et ne justifie pas Slow Start

**Recouvrement rapide** pour résoudre rapidement la perte de segments isolés \( en combinaison avec retransmission rapide\)

### Algorithme de recouvrement rapide

* Retransmettre rapidement le segment manquant
* Diminuer la fenêtre à la moitié
* Continuer avec Congestion Avoidance

![Effet de fast recovery sur le d&#xE9;bit](../../.gitbook/assets/image%20%28125%29.png)

## Résumé du contrôle de congestion

La taille de la fenêtre de congestion est variée en fonction de la congestion du réseau. Une congestion est détectée à cause de pertes de paquets

#### Slow Start

* Au début de la connexion et après un timeout de retransmission \(→congestion sévère\)
* Permet d’augmenter rapidement le débit

#### Congestion avoidance

* Dès que le débit s’approche à la capacité disponible

#### Seuil d'évitement de congestion ssthresh

* Indique la zone critique où une congestion est possible
* Accroissement additif et décroissance multiplicative de ssthresh
* Ssthresh oscille entre le débit maximum et la moitié de ce débit



