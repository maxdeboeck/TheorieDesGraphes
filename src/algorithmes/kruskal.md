# Algorithme de Kruskal

## Maths/Description

In : 
$G=(N,R)$ un graphe connexe pondéré

Out : 
$(N,R')$ un arbre sous-tendant $G$ de poids minimum

Init : 
On définit $R_{\text{ord}}$ l'ensemble trié des arêtes pondérées venant de $R$ ainsi que $R':=\emptyset$ 

Loop :
Tant que $|R'|\lt |N|-1$ :
- $(\alpha, R_{\text{ord}}):=R_{\text{ord}}$ (on retire la première arête $\alpha$ de l'ensemble trié $R_{\text{ord}}$)
- Si $(N,R' \cup \{\alpha\})$ est sans cycle, alors $R':=R' \cup \{\alpha\}$ (une condition équivalente est : Si l'arête relie 2 arbres ***distincts*** alors...) 

<p style="text-align: center;">
<img src="../assets/algorithmes/KruskalDemo.gif" style="width:50%;height:auto;"/>
</p>

---

## Implémentation Python

```python
# Cette fonction admet l'existance de certaines 
# méthodes et classes qui permettent de rendre
# le code plus lisible.
def kruskal(graph, rPrime):
    graph.sortByWeight()

    for edge in graph.edges():
        weight, u, v = edge
        if hasCycle(rPrime.union(edge)) == false:
            rPrime = rPrime.union(edge)

    return rPrime
```
### Complexité 
Spatiale : $O(|N|+|V|)$

Temporelle : dépend surtout de l'algorithme de triage mais dans le meilleur des cas : $O(|R|\log|R|)=O(|R|\log|E|)$

---

## Preuve de validité

Todo