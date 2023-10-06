# Algorithme de Bellman-Ford

## Maths

In : 
$G=(N,R)$ un graphe orienté pondéré ***sans cycle négatif*** et $s \in N$

Out : 
Une liste de taille $|N|$ contenant les distances minimales séparant $s$ de tous les autres nœuds. 

Init : 
$d(s):=0$ et $d(u):=\infty \,\,\, \forall u \in N -\{s\}$. On créé une liste de distances séparant $s$ des autres nœuds. On initialise les distance à une valeur de $\infty$ pour que les comparaisons qui suivent puissent rapidement remplacer cette valeur et la distance séparant $s$ de $s$ est $0$.

Loop :
Répète $|N|-1$ fois :
- $\forall(u,v)\in R:$
  - si $d(u)+c((u,v))\lt d(v)$ alors $d(v):=d(u)+c((u,v))$

---

## Description 

1. On créé la liste $d$ 
2. Ensuite on répète $|N|-1$ fois la procédure suivante
3. Pour chaque arête reliant $u$ à $v$ on regarde si la distance à l'arête $v$ peut être raccourcie en prenant la distance à l'arête $u$ plus le poids de l'arête qui les sépare.
4. $d$ contient les valeurs recherchées.

---

## Implémentation Python

```python
# Cette fonction admet qu'il n'y a pas de cycle négatif dans le graphe. 
def bellman_ford(graph, source):

    distance = {vertex: float('infinity') for vertex in graph}
    distance[source] = 0

    for i in range(len(graph) - 1):
        for u, v, weight in graph.edges():
            if distance[u] + weight < distance[v]:
                distance[v] = distance[u] + weight

    return distance
```
### Complexité 
Spatiale : $O(|N|)$

Temporelle : $O(|N|\cdot|R|)$

---

## Preuve de validité
### Preuve par induction
#### Observations :
Après $i$ répétitions :
1. Si $d_{i}(u)\neq \infty$, alors $d_{i}(u)$ est le coût d'un chemin de $s$ vers $u$ (pas forcément le plus court)
2. Si $\exists$ un chemin de $s$ vers $v$ d'au plus $i$ arêtes, alors $d_{i}(v)$ est $\leq$ au coût du plus court chemin de $s$ vers $v$ comptant au plus $i$ arêtes

Si on arrive à démontrer ces observations on aura démontré que l'algorithme est correct.

#### Cas initial :
On a $d_{0}(s)=0$ et $d_{0}(u)=\infty \,\,\, \forall u \in N -\{s\}$

#### Cas général :
Si $d_{i}(v)$ a été mis à jour selon la formule $d_{i-1}(u)+c((u,v))$ alors $d_{i}(v)$ est la longueur du chemin allant de $s$ à $v$ qui suit le chemin allant de $s$ à $u$ et ensuite vers $v$. Ce qui prouve la première observation.

Pour la seconde observation, si on considère un chemin de longueur minimale $C(i)$ (il peut y en avoir plusieurs) allant de $s$ à $v$ avec au plus $i$ arêtes. Soit $u$ le dernier nœud avant $v$. Alors, le chemin allant de $s$ à $u$ dans $C(i)$ (qu'on peut noter $Q$) est un chemin de longueur minimale avec au plus $i-1$ arêtes parce que sinon il y aurait un chemin plus court avec au plus $i$ allant de $s$ à $v$ que $C(i)$ ce qui est une contradiction. 

Nous faisons maintenant l'hypothèse inductive que $d_{i-1}(u)=w(Q)$ ($w$ étant la fonction qui donne la somme des poids des arêtes d'un parcours).

À l'itération $i$ on calcule $d_{i}(v)=\text{min}(d_{i-1}(v),d_{i-1}(u)+c((u,v)))$
On sait que $d_{i-1}(u)+c((u,v))=w(Q)+c((u,v))=w(P)$ on a donc que $d_{i}(v)\leq w(P)$ ce qui démontre la seconde observation.

Comme il n'y a pas de cycle négatif le chemin le plus court ne passera pas plus d'une fois par chacun des nœuds et donc après $|N|-1$ cycles nous auront toujours le chemin le plus court.

Preuves externes :
1. [MIT](https://web.stanford.edu/class/archive/cs/cs161/cs161.1168/lecture14.pdf)
2. Wikipedia [EN](https://en.wikipedia.org/wiki/Bellman%E2%80%93Ford_algorithm#Proof_of_correctness), [FR](https://fr.wikipedia.org/wiki/Algorithme_de_Bellman-Ford#Preuve_de_la_correction)
