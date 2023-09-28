# Algorithme de Bellman-Ford

In : 
$ G=(N,R)$ un graphe orienté pondéré ***sans cycle négatif*** et $ s \in N$

Out : 
Le coût du + court chemin de $ s$ vers tout $ n \in N$ 

Init : 
$ d(s):=0$ et $ d(i):=\infty \,\,\, \forall i \in N -\{s\}$. On créé une liste de distances séparant $ s$ des autres nœuds. On initialise les distance à une valeur de $ \infty$ pour que les comparaisons qui suivent puissent rapidement remplacer cette valeur et la distance séparant $ s$ de $ s$ est $ 0$.

Loop :
Répète $ |N|-1$ fois :
	$ \forall(i,j)\in R:$
		si $ d(i)+c((i,j))\lt d(j)$ alors $ d(j):=d(i)+c((i,j))$

Result :
Une liste de taille $ |N|$ contenant les distances minimales séparant $ s$ de tous les autres nœuds. 


Description :
1. On créé la liste $ d$ 
2. Ensuite 
