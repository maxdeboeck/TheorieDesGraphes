# Matrices

## 1. Matrice incidente :
La matrice d’incidence d’un graphe $ G=(n,R)$ est la matrice de genre $ |N|\times|R|$ dont chaque entrée $ (i,\alpha)\in N\times R$ vaut :
- $ 2$ si l’arête $ \alpha$ est une boucle sur le nœud $ i$,
- $ 1$ si $ \alpha$ relie $ i$ à un autre nœud,
- $ 0$ si $ \alpha$ n’est pas incidente à i.
<!-- ![[Pasted image 20230928092639.png]] -->

##  2. Matrice Adjacente :
La matrice d’adjacence $ A$ est de genre $ |N|\times|N|$ : 
- $ a_{i,j}:=$  nombre d’arêtes reliant $ i$ et $ j$ si $ i \neq j$ 
- $ a_{i,i}:=$ deux fois le nombre de boucles sur $ i$

![test](../assets/plswork.png)

***Propriétés/Théorèmes :***
- 2.1 : $ \sum_{j\in N}a_{i,j}=\sum_{j\in N}a_{j,i}=\text{deg}(i)$ La somme des termes sur une lignes ou une colonne correspond au degré du nœud associé à cette ligne/colonne.
- 2.2 : $ \sum_{(i,j)\in N^{2}}a_{i,j}=2|R|$ La somme de tous les éléments de la matrice est égal au double du nombre d'arêtes dans le graphe.
- 2.3 : $ \sum_{i \in N}\text{deg}(i)=2|R|$ La somme des degrés des nœuds d'une graphe est égal au double du nombre d'arêtes dans le graphe.

##  3. Isomorphisme :
Les graphes simples $ G=(N,R)$ et $ G'=(N',R')$ sont isomorphes si : 
1. Il existe une bijection $ f:N\rightarrow N'$
2. $ \{i,j\}\in R \Leftrightarrow \{f(i),f(j)\}\in R'$
***Propriétés/Théorèmes :***
	2.1 : La relation d'isomorphisme est une relation d'équivalence sur les graphes
	2.2 : Il est facile de vérifier si $ f$ définit un isomorphisme Il reste difficile de décider si deux graphes sont isomorphes