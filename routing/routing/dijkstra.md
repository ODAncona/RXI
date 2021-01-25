---
description: Le chemin le plus court
---

# Algorithme de Dijkstra

1. Préparation: 
   * Représenter le réseau par un graphe 
   * Pondérer chaque arête k par un coût pk 
2. Marquer chaque nœud par un doublet $$ (C_i, N_x)$$ 
   * $$C_i$$ : Distance totale depuis la source
   * $$N_x$$ : Nœud précédent \(pour reconstruire le chemin\) 
   * Doublet de chaque nœud initialisé à $$(\infty,-)$$ 
   * Sauf le nœud d’origine initialisé à$$(0,-)$$ 
3. Choisir le nœud $$N_i$$avec le coût $$C_i$$le plus bas et qui n’est pas marqué et le marquer comme ‘permanent’
4. Calculer les coûts des chemins de tous les voisins $$N_j$$ du nœud 

   $$N_i$$ : $$C_j = C_i + p_k$$ 

5. Si la nouvelle valeur $$C_j$$ est plus petite que l’ancienne, --&gt; actualiser le doublet de $$N_j$$ : $$(C_j, N_i)$$ 
6. Répéter 2 à 4 jusqu’à ce que la destination soit marquée ‘permanent’

## Exemple

### 1. Préparation

![Graphe initial avec le poids sur chaque lien](../../.gitbook/assets/image%20%2838%29.png)

### 2. Initialisation

![Ajout d&apos;un doublet &#xE0; chaque n&#x153;ud](../../.gitbook/assets/image%20%2881%29.png)

### 3. Déroulement

![S&#xE9;lection du n&#x153;ud A non permanent avec cout minimal](../../.gitbook/assets/image%20%2891%29.png)

![Calcul des chemins depuis le n&#x153;ud permanent A](../../.gitbook/assets/image%20%28112%29.png)

![S&#xE9;lection du n&#x153;ud B non permanent avec cout minimal](../../.gitbook/assets/image%20%2887%29.png)

![Calcul des chemins depuis le n&#x153;ud permanent B](../../.gitbook/assets/image%20%2846%29.png)

![S&#xE9;lection du n&#x153;ud E non permanent avec cout minimal](../../.gitbook/assets/image%20%2836%29.png)

![Calcul des chemins \(E\) + actualisation du doublet G](../../.gitbook/assets/image%20%28105%29.png)

![S&#xE9;lection du n&#x153;ud G non permanent avec cout minimal](../../.gitbook/assets/image%20%2825%29.png)

![Calcul des chemins depuis le n&#x153;ud permanent G](../../.gitbook/assets/image%20%2868%29.png)

![S&#xE9;lection du n&#x153;ud F non permanent avec cout minimal](../../.gitbook/assets/image%20%2848%29.png)

![Calcul des chemins \(F\) + actualisation des doublets C et H](../../.gitbook/assets/image%20%2845%29.png)

![S&#xE9;lection du n&#x153;ud H non permanent avec cout minimal](../../.gitbook/assets/image%20%28106%29.png)

![Calcul des chemins depuis le n&#x153;ud permanent H](../../.gitbook/assets/image%20%2815%29.png)

![S&#xE9;lection du n&#x153;ud C non permanent avec cout minimal](../../.gitbook/assets/image%20%2871%29.png)

![S&#xE9;lection du n&#x153;ud D non permanent avec cout minimal](../../.gitbook/assets/image%20%2818%29.png)

{% hint style="success" %}
Meilleure route trouvée !
{% endhint %}



{% page-ref page="dijkstra.md" %}

