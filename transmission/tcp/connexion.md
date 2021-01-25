# Etablir une connexion

L'établissement d'une connexion n'est pas simple. On ne peut pas simplement demander d'établir la connexion et de le confirmer.

![Protocole non fonctionnel](../../.gitbook/assets/image%20%281%29.png)

{% hint style="danger" %}
Non fonctionnel ! Si certains paquets sont retardés, on peut avoir deux demandes et confirmations en différé .\(double paiement etc...\)
{% endhint %}

## Etablissement d'une connexion

* Le protocole doit tenir compte de la possibilité de doublons
* Threeway Handshake
  * Les hôtes se mettent d’accord sur les numéros de séquence initiaux
  * Lors d’une erreur, un message RST \(RESET\) permet d’interrompre l’établissement de connexion

![](../../.gitbook/assets/image%20%28131%29.png)

## Libération d’une connexion

Les connexions TCP sont bidirectionnelles

Libération séparément dans les deux sens:

* Un hôte qui n’a plus de données à transmettre peut fermer la connexion dans une direction
* L’autre hôte peut continuer à transmettre

Deux segments pour libérer un sens de la connexion: FIN + ACK

![L&apos;h&#xF4;te A n&apos;a plus rien &#xE0; transmettre et ferme la connexion](../../.gitbook/assets/image%20%282%29.png)

