# Algorithme DBSCAN - Explication

## Description
L'algorithme **DBSCAN** (Density-Based Spatial Clustering of Applications with Noise) est une méthode de **clustering non supervisée** qui permet de regrouper des points de données en clusters basés sur la densité de ces points. Contrairement à des algorithmes comme **K-Means**, DBSCAN ne nécessite pas de spécifier le nombre de clusters à l'avance et peut gérer des données de formes variées.

Le principe de DBSCAN repose sur trois concepts clés :

- **Points de cœur (core points)** : Ce sont des points ayant un certain nombre minimum de voisins dans une zone autour d'eux.
- **Points de bordure (border points)** : Ce sont des points ayant moins de voisins dans leur voisinage, mais qui se trouvent à proximité d'un point de cœur.
- **Points de bruit (noise points)** : Ce sont des points qui ne peuvent être assignés à aucun cluster, car ils n'ont pas suffisamment de voisins pour être considérés comme des points de cœur.

L'algorithme cherche donc à identifier des zones de forte densité (clusters) tout en séparant les points de bruit.

## Jeu de données utilisé
L'algorithme DBSCAN que nous avons implémenté utilise un jeu de données artificiel généré à l'aide de distributions normales. Ces données contiennent trois groupes de points ayant des caractéristiques différentes, permettant de tester l'algorithme dans un scénario où les clusters sont bien définis par des zones de densité différente. L'objectif est de voir comment DBSCAN peut séparer ces groupes et identifier les points de bruit.

**Exemple de jeu de données :**
- **Caractéristique 1** : Mesure continue de la première variable (par exemple, la taille).
- **Caractéristique 2** : Mesure continue de la deuxième variable (par exemple, le poids).

Ces données sont générées à partir de trois distributions normales distinctes, chacune représentant un groupe.

## Étapes de l'algorithme DBSCAN

### 1. Initialisation des paramètres
L'algorithme commence par l'initialisation de deux paramètres :
- **Epsilon (ε)** : La distance maximale entre deux points pour qu'ils soient considérés comme voisins.
- **MinPoints** : Le nombre minimum de points requis pour qu'un point soit considéré comme un point de cœur.

### 2. Calcul des distances
DBSCAN commence par calculer la distance entre chaque point et tous les autres points du jeu de données, généralement avec la distance euclidienne. Ces distances sont ensuite utilisées pour déterminer si un point appartient à un cluster.

### 3. Identification des points de cœur, de bordure et de bruit
- Si un point a au moins **MinPoints** voisins dans un rayon de **ε**, il est un **point de cœur**.
- Si un point a moins de **MinPoints** voisins mais se trouve à proximité d'un point de cœur, il est un **point de bordure**.
- Les points qui ne remplissent aucune de ces conditions sont des **points de bruit**.

### 4. Expansion des clusters
Lorsqu'un **point de cœur** est trouvé, DBSCAN étend un cluster autour de ce point en incluant tous les voisins proches. Cela peut entraîner l'ajout de nouveaux points de cœur et l'expansion du cluster. Ce processus se répète jusqu'à ce qu'aucun autre point ne puisse être ajouté au cluster.

### 5. Réitération jusqu'à traitement de tous les points
L'algorithme parcourt l'ensemble du jeu de données, en traitant chaque point une fois et en l'assignant à un cluster ou en le classifiant comme un point de bruit.

### 6. Résultat final
Le résultat final de l'algorithme est un ensemble de **clusters** (s'il y en a) et des **points de bruit**. Les clusters sont définis par les points de cœur et leurs voisins directs. Les points de bruit sont des points isolés qui ne font pas partie de ces zones de densité élevée.

## Détails supplémentaires

### Distance Euclidienne
La distance euclidienne est la méthode la plus courante pour mesurer la proximité entre deux points. La formule de la distance euclidienne entre deux points `a = (a1, a2, ..., an)` et `b = (b1, b2, ..., bn)` dans un espace à n dimensions est donnée par :

$$ D(a, b) = \sqrt{\sum_{i=1}^{n} (a_i - b_i)^2} $$

### Paramètres importants :
- **Epsilon (ε)** : La taille du voisinage autour d'un point.
- **MinPoints** : Le nombre minimum de points dans le voisinage pour qu'un point soit considéré comme un point de cœur.

## Points forts de DBSCAN
- **Pas besoin de spécifier le nombre de clusters** : Contrairement à K-Means, DBSCAN n'a pas besoin d'un nombre prédéfini de clusters.
- **Capacité à identifier les points de bruit** : DBSCAN peut séparer les points aberrants ou les points de bruit, ce qui n'est pas toujours possible avec d'autres algorithmes.
- **Clustering de forme arbitraire** : DBSCAN peut trouver des clusters de formes arbitraires, contrairement à K-Means qui est limité à des clusters de forme sphérique.

## Limites de DBSCAN
- **Choix des paramètres** : Le choix de **ε** et de **MinPoints** peut être difficile et dépend du jeu de données. Une mauvaise sélection de ces paramètres peut nuire à la qualité du clustering.
- **Densité variable des clusters** : DBSCAN a du mal à identifier des clusters ayant des densités très différentes.
- **Coût computationnel** : Le calcul des distances peut être coûteux pour de très grands jeux de données.

## Applications de DBSCAN
DBSCAN est utilisé dans de nombreux domaines, notamment :
- **Détection de communautés** : Identifier des groupes d'objets ou d'individus dans un réseau.
- **Analyse géospatiale** : Identifier des zones denses dans des cartes géographiques, comme des zones urbaines ou des points d'intérêt.
- **Clustering d'images** : Pour le regroupement d'images ou d'objets dans des images en fonction de leurs caractéristiques.

## Conclusion
DBSCAN est un algorithme de clustering très efficace lorsqu'il s'agit de gérer des données de formes variées et de détecter des anomalies. Sa capacité à identifier des points de bruit et à ne pas nécessiter de spécification du nombre de clusters en fait un choix populaire pour de nombreuses applications de clustering. Cependant, le choix de ses paramètres (**ε** et **MinPoints**) reste un défi, et l'algorithme peut être sensible aux variations de densité des clusters.
