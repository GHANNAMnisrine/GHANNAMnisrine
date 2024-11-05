- 👋 Hi, I’m @GHANNAMnisrine
- 👀 I’m interested in statistics and data science
- 🌱 Take a look on how you can build a hierarchical function on python from scratch

# Hierarchical Clustering from Scratch with Python

Ce projet implémente un algorithme de **clustering hiérarchique ascendant (agglomératif)** développé entièrement en Python. Il présente une alternative aux bibliothèques de machine learning en reproduisant cette méthode de clustering depuis les principes de base, illustrant ainsi une solide compréhension des algorithmes de clustering et des structures de données.

## Description du Projet

Le clustering hiérarchique est une technique de machine learning non supervisée permettant de regrouper des données en clusters. Dans cette approche, chaque observation commence comme un cluster unique, et l'algorithme fusionne progressivement les clusters les plus proches jusqu'à atteindre un certain nombre de clusters souhaité.

### Étapes clés de l'implémentation

1. **Génération des Données Synthétiques** : Les données d'entraînement sont générées à l'aide de distributions normales afin de créer des clusters naturels avec différentes moyennes et variances. Cela permet d'observer le comportement de l'algorithme sur des données non linéaires.

2. **Calcul de la Distance Euclidienne** : Un calcul personnalisé de la distance euclidienne est utilisé pour mesurer la proximité entre les points. Cette distance sert de critère pour décider quels clusters fusionner à chaque étape.

3. **Initialisation des Clusters** : Chaque point est initialement assigné à son propre cluster. L'algorithme fusionne ensuite les clusters deux à deux selon la distance calculée jusqu’à réduire le nombre de clusters à un niveau souhaité.

4. **Fusion des Clusters les Plus Proches** : Pour chaque itération, l'algorithme identifie les deux clusters les plus proches, puis les fusionne. Cette étape est répétée jusqu’à atteindre le nombre de clusters demandé par l'utilisateur.

5. **Visualisation des Clusters et du Dendrogramme** : Des graphiques en deux dimensions et un dendrogramme illustrent visuellement les clusters formés et montrent les distances entre eux. Ces visualisations facilitent l'évaluation de la séparation et de la cohésion entre les clusters.

6. **Évaluation avec le Coefficient de Silhouette** : Le coefficient de silhouette est utilisé pour évaluer la qualité des clusters. Il quantifie à quel point les points sont bien regroupés dans leurs clusters respectifs et séparés des autres clusters, offrant ainsi une mesure objective de la qualité du clustering.

### Compétences mises en avant

- **Maîtrise des mathématiques appliquées** : en particulier les calculs de distance et la logique de clustering.
- **Développement d’algorithmes à partir de zéro** : utilisation de Python pour reproduire un algorithme de machine learning sans dépendance à une bibliothèque d’apprentissage automatique.
- **Visualisation de données** : création de visualisations interprétables pour faciliter la compréhension des clusters formés et évaluer la performance du modèle.
- **Évaluation des modèles de clustering** : intégration de métriques comme le coefficient de silhouette pour quantifier l'efficacité de l'algorithme.

### Visualisation des Résultats

Les résultats finaux sont présentés sous forme de graphiques qui montrent chaque cluster en couleur distincte ainsi qu'un dendrogramme détaillant le processus de fusion des clusters. Cette visualisation fournit une perspective intuitive et analytique de la manière dont les clusters sont formés et comment ils se distinguent les uns des autres.

