# Algorithme K-Means - Explication

## Description

L'algorithme K-means est une méthode de **clustering** (ou regroupement) non supervisée, utilisée pour partitionner un ensemble de données en `k` groupes (ou clusters) basés sur leur similarité. Chaque cluster est défini par son **centroid**, qui est la moyenne des points de données appartenant à ce cluster.

Le but de K-means est de minimiser la somme des distances entre chaque point de données et son centroid respectif. Cet algorithme est largement utilisé dans des domaines comme l'apprentissage automatique, l'analyse de données, et la segmentation de marché.

## Jeu de données utilisé

L'algorithme K-means que nous avons implémenté dans ce projet utilise comme base un **jeu de données spécifique**, choisi pour illustrer l'application du clustering dans un contexte donné. Ce jeu de données peut être constitué de différentes caractéristiques (comme des mesures de produits, des données démographiques, etc.) et est souvent utilisé pour démontrer les performances de l'algorithme K-means.

L'algorithme est appliqué pour identifier des **groupes naturels** au sein des données, ce qui peut aider à extraire des informations significatives, comme des segments de clients similaires ou des comportements partagés au sein d'un ensemble de données.

### Exemple de jeu de données :

- **Colonnes possibles** :
  - *Caractéristique 1* : Description de la première variable.
  - *Caractéristique 2* : Description de la deuxième variable.
  - *(Et ainsi de suite…)*

Le jeu de données peut être utilisé pour montrer comment K-means regroupe les points en fonction de leurs caractéristiques communes.

## Étapes de l'algorithme K-Means

### 1. **Initialisation des Centroids**

L'algorithme commence par **initialiser aléatoirement** `k` centroids. Ces centroids sont généralement choisis parmi les points de données existants ou de manière totalement aléatoire.

### 2. **Assignation des points aux clusters**

Ensuite, pour chaque point de données, l'algorithme calcule la distance à chacun des centroids existants (habituellement, la distance euclidienne). Chaque point est ensuite **assigné au centroid le plus proche**, formant ainsi un groupe de points (un cluster).

### 3. **Calcul des nouveaux Centroids**

Après l'assignation des points, l'algorithme recalculera la position de chaque centroid en prenant la **moyenne** des points qui lui ont été attribués. Ce recalcul déplace les centroids vers le centre des points qui leur sont associés.

### 4. **Réitération jusqu'à convergence**

Les étapes d'assignation des points et de recalcul des centroids sont répétées jusqu'à ce que les centroids ne changent plus de manière significative, ou jusqu'à ce qu'un nombre maximum d'itérations soit atteint. À ce stade, l'algorithme a convergé et les clusters sont considérés comme stables.

### 5. **Résultat final**

Le résultat final de l'algorithme est un ensemble de `k` clusters, où chaque cluster contient des points qui sont proches les uns des autres et éloignés des autres clusters. Les centroids finaux représentent les moyennes des points dans chaque cluster.

## Détails supplémentaires

- **Distance Euclidienne** : C'est la méthode la plus courante pour mesurer la proximité entre un point et un centroid. La formule de la distance euclidienne entre deux points \( x = (x_1, x_2, ..., x_n) \) et \( y = (y_1, y_2, ..., y_n) \) dans un espace à `n` dimensions est donnée par :

  \[
  D(x, y) = \sqrt{\sum_{i=1}^{n} (x_i - y_i)^2}
  \]

- **K** : Le nombre de clusters `k` doit être défini avant l'exécution de l'algorithme. Ce nombre peut être choisi en fonction du domaine d'application ou en utilisant des méthodes comme la méthode du **coude** (Elbow Method) pour déterminer le nombre optimal de clusters.

## Points forts de K-Means

- **Simplicité et rapidité** : L'algorithme est relativement simple à comprendre et à implémenter. Il peut également être très rapide pour des ensembles de données de grande taille.
- **Flexibilité** : K-means peut être utilisé pour différents types de données (bien qu'il fonctionne mieux pour des données continues).
- **Scalabilité** : L'algorithme est scalable et peut être appliqué à de grandes bases de données.

## Limites de K-Means

- **Choix du nombre de clusters** : Le nombre de clusters `k` doit être défini avant l'exécution de l'algorithme, ce qui peut être difficile sans connaissance préalable des données.
- **Sensibilité aux initialisations** : L'algorithme est sensible à l'initialisation des centroids. Si les centroids initiaux sont mal choisis, l'algorithme peut converger vers un minimum local plutôt qu'un optimum global.
- **Données non sphériques** : L'algorithme K-means peut ne pas fonctionner efficacement si les données ne sont pas distribuées en formes sphériques ou si les clusters ont des tailles et des densités inégales.
- **Outliers** : Les points de données aberrants (outliers) peuvent affecter les résultats du clustering en influençant de manière disproportionnée la position des centroids.

## Applications de K-Means

K-means est utilisé dans divers domaines et applications, tels que :

- **Segmentation de marché** : Identifier des groupes de consommateurs ayant des comportements similaires.
- **Compression d'image** : Réduire la taille d'une image en regroupant les pixels similaires.
- **Analyse de données géospatiales** : Identifier des zones géographiques avec des caractéristiques similaires.
- **Classification d'images et de textes** : Clustering d'images ou de documents en groupes basés sur leur contenu.

## Conclusion

L'algorithme K-means est un puissant outil de regroupement non supervisé, capable de partitionner efficacement des données en clusters. Cependant, pour obtenir de bons résultats, il est important de bien choisir le nombre de clusters et de faire attention aux initialisations des centroids. Des variantes de K-means, comme K-means++, ont été proposées pour résoudre certains des problèmes liés à l'initialisation et améliorer les résultats de l'algorithme.

