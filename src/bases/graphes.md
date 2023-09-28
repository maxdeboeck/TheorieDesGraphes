# Graphes

### Définitions

#### ***Base*** :

##### 0.1 Nœud/Sommet/Point :
Unité fondamentale d'un graphe

***Propriétés/Théorèmes :***
	0.1.1 : Deux sommets sont voisins s'ils sont reliés par une arête.
	0.1.2 : Deux sommets sont indépendants s'ils ne sont pas voisins.
	0.1.3 : Le ***degré*** d'un sommet est le nombre d'arêtes incidentes à ce sommet les boucles (0.3.1) comptant double.

##### 0.2 Graphe :
Un graphe est un triple $ G=(N,R,I)$ :
- $ N :$ ensemble fini nœuds notés $ (i,j,k,\dots)$
- $ R :$ ensemble fini d'arêtes notées ($ \alpha,\beta,\boldsymbol{\gamma}\dots$)
- $ I :$ une relation d'incidence $ \subset N\times R$ telle que toute arête est incidente à 1 ou 2 nœuds (cette relation est généralement sous-entendue pour un graphe donné)
***Propriétés/Théorèmes :***
	0.2.1 : Un graphe $ G$ est dit d'ordre $ n$ si $ |N|=n$

##### 0.3 Arête/Lien/Ligne :
liaison entre deux sommets d'un graphe

***Propriétés/Théorèmes :***
	0.3.1 : Une arrête $ \alpha \in R$ est une boucle si $ |\{i|(i,\alpha)\in I\mid=1$ :
		1. $ (i,\alpha) \in I$ : Indique que la paire $ (i,\alpha)$ est un élément de l'ensemble $ I$.
		2. $ i|(i,\alpha) \in I$ : Désigne l'ensemble des $ i$ tels que $ (i,\alpha)$ ce trouve dans l'ensemble des relations d'incidence c'est à dire l'ensemble des connexions arête nœud.
		3. $ |\{i|(i,\alpha)\in I \mid$ Désigne la taille de l'ensemble susmentionné.


#### ***Dérivées*** :

##### 1.0 Graphe Eulérien :
Graphe possédant au moins un cycle eulérien (1.1).
***Exemples :***
1 :
  ![[bitmap 2.png]]
2 :
  ![[bitmap 5.png]]
***Propriétés/Théorèmes :***
	1.0.1 : Un graphe connexe (1.2) dont les nœuds sont tous de degré pair est un graphe eulérien et inversement.
	1.0.2 :

##### 1.1 Cycle/Circuit Eulérien :
Parcours eulérien (1.3) qui revient au sommet/nœud de départ

##### 1.2 Graphe Connexe :
Un graphe est connexe si il existe un parcours reliant toute paire de nœuds.

##### 1.3 Parcours/Chemin/Chaine eulérien(ne) :
Un chemin qui passe par toutes les arêtes, une seule fois.

***Propriétés/Théorèmes :***
	1.0.1. : Un graphe connexe a un parcours eulérien si il possède 0 ou 2 arêtes de degré impair.

##### 1.4 Graphe Simple :
Un graphe est simple si il n’a ni boucle ni nœuds reliés par des arêtes
multiples. $ \alpha=\{i,j\}$ identifie alors l'unique arête telle que $ (i,\alpha)\in I$ et $ (j,\alpha) \in I$

***Propriétés/Théorèmes :***
	1.4.1 : Un graphe simple est biparti si et seulement s'il ne possède aucun cycle de longueur impaire (explication de la partie nécessaire de cette équivalence : Si on imagine un cycle de longueur 3, on place un nœud dans $ U$ et dans $ V$, où place-t-on le troisième nœud ? Dans les 2 cas on aura une arête avec ses extrémités dans un même ensemble  )
	1.4.2 : Un graphe simple non orienté d'ordre $ n$ a au maximum $ \frac{n(n-1)}{2}$ arêtes

##### 1.5 Graphe Biparti :
Un graphe est dit biparti si son ensemble de sommets peut être divisé en deux sous-ensembles disjoints $ U$ et $ V$ tels que chaque arête ait une extrémité dans $ U$ et l'autre dans $ V$. 

##### 1.6 Cycle :
Un cycle est une suite d'arêtes consécutives distinctes (chaine simple) dont les deux sommets extrémités sont identiques.

##### 1.7 Isthme :
Considérons un graphe connexe $ G=(N,R)$. Une arête $ \alpha \in R$ est appelée un isthme de $ G$ si la présence de $  \alpha$ est indispensable à la connexité, c’est-à-dire si le graphe partiel $ G_{\alpha}^{*} :=(N,R\backslash\{\alpha\})$ n’est pas connexe.

##### 1.7 Arbre :
Un arbre est un graphe connexe qui ne possède pas de cycle.

***Propriétés/Théorèmes :***
	***Les Propriétés suivantes sont équivalentes (elles définissent des arbres)*** :
	1.7.1 : $ G$ est connexe et sans cycle.
	1.7.2 : $ G$ est connexe et $ |R|=|N|-1$
	1.7.3 : $ G$ est sans cycle et $ |R|=|N|-1$ 
	1.7.4 : $ G$ est sans cycle et lui ajouter une arête crée un et un seul cycle.
	1.7.5 : $ G$ est connexe et supprimer une arête quelconque le déconnecte.
	1.7.6 : Deux nœuds distincts de $ G$ sont reliés par un et un seul chemin (et $ G$ est sans boucle)

##### 1.8 Feuille :
Soit $ G=(N,R)$ un arbre. On dit qu’un nœud $ n\in N$ est une feuille de $ G$ si $ \text{deg}(n)=1$.

***Propriétés/Théorèmes :***
	1.8.1 : Les extrémités du chemin le plus long dans un arbre sont des feuilles de degré 1. 
	Preuve : 
	Soit $ c=(n_{1},n_{2},\dots,n_{m})$ un chemin de longueur maximale dans $ G$ (ce chemin n’est pas nécessairement unique, mais il en existe au moins un). On voit que $ \text{deg}(n_{1}) \geq 1$ puisque $ n_{1}$ est adjacent à $ n_{2}$. Si $ n_{1}$ était de degré strictement supérieur à $ 1$, il devrait exister un nœud $ n$ adjacent à $ n_{1}$ et distinct de $ n_{2}$. Si $ n$ se trouve sur le chemin défini plus haut, alors $ G$ possède un cycle, ce qui contredit le fait que $ G$ est un arbre. Si $ n$ ne se trouve pas sur le chemin défini plus haut, alors $ c$ peut être étendu en le préfixant par $ n$, ce qui contredit l’hypothèse que $ c$ est un chemin de longueur maximale. On en conclut que $ \text{deg}(n_1)=1$. Le même raisonnement s’applique à $ n_{m}$, et on a donc identifié deux nœuds de degré $ 1$.

##### 1.9 Chemin :
Un chemin est un parcours ouvert dont tous les nœuds sont distincts.

***Propriétés/Théorèmes :***
	
