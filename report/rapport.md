# Analyse et estimation des prix immobiliers à l’aide du Machine Learning

## 1. Introduction

Dans le cadre du module *Data Science & Machine Learning*, ce projet s’inscrit dans une
problématique de **Marketing & Commerce**, plus précisément dans l’**estimation des prix
immobiliers**. L’objectif est de transformer un jeu de données brut en informations
exploitables, puis de développer des modèles prédictifs capables d’expliquer et d’anticiper
le prix des maisons.

Le projet vise deux objectifs principaux :
- modéliser le prix des maisons à l’aide d’un modèle de régression,
- classifier les maisons en catégories de prix (élevé / bas) afin d’aider à la prise de décision.

---

## 2. Présentation du Dataset

Le jeu de données utilisé provient de la plateforme Kaggle (*Home Value Insights*).
Il contient environ **1 000 observations**, chaque ligne représentant une maison décrite
par plusieurs caractéristiques.

### Variable cible
- **House_Price** : prix de la maison (variable quantitative continue).

### Variables explicatives
Les variables explicatives décrivent les caractéristiques physiques des maisons, notamment :
- la surface habitable (*Square_Footage*),
- la taille du garage (*Garage_Size*),
- la taille du terrain (*Lot_Size*),
- d’autres variables numériques secondaires.

Le problème étudié est à la fois :
- un **problème de régression** (prédiction continue du prix),
- un **problème de classification binaire**, après transformation du prix.

---

## 3. Méthodologie

### 3.1 Prétraitement des données

Les étapes de prétraitement incluent :
- la vérification des types de variables,
- l’identification des valeurs manquantes,
- la séparation entre les variables explicatives et la variable cible.

Pour la régression logistique, une **standardisation** des variables numériques a été appliquée
afin d’assurer une convergence stable du modèle.

### 3.2 Analyse Exploratoire des Données (EDA)

L’analyse exploratoire a permis d’étudier :
- la distribution du prix des maisons,
- les relations entre les variables numériques et la variable cible.

L’étude de corrélation montre que **la surface habitable (Square_Footage)** et **la taille du
garage (Garage_Size)** sont les variables les plus fortement corrélées au prix.
La variable *Square_Footage* a été retenue comme variable explicative principale.

Chaque graphique a été accompagné d’une interprétation afin de justifier les choix
effectués pour la modélisation.

---

## 4. Modélisation

### 4.1 Régression linéaire

La régression linéaire a été utilisée pour modéliser la relation entre le prix des maisons et
la surface habitable.

Le modèle met en évidence une relation linéaire positive : plus la surface augmente,
plus le prix de la maison augmente. Ce résultat est cohérent avec l’analyse exploratoire.

### 4.2 Régression logistique

Afin de transformer le problème en classification, la variable *House_Price* a été convertie
en une variable binaire :
- 1 : prix supérieur à la médiane,
- 0 : prix inférieur ou égal à la médiane.

La régression logistique permet d’estimer la probabilité qu’une maison appartienne à la
catégorie des maisons à prix élevé en fonction de sa surface.

---

## 5. Résultats et Discussion

### 5.1 Matrice de confusion

La matrice de confusion permet d’analyser les erreurs de classification du modèle.
Elle distingue les vrais positifs, les vrais négatifs, ainsi que les faux positifs et faux négatifs.
Les résultats montrent que le modèle classe correctement une majorité des observations.

### 5.2 Courbe ROC et AUC

La courbe ROC évalue la capacité du modèle à discriminer entre les maisons à prix élevé et
à prix bas pour différents seuils de décision.
Le score AUC obtenu indique une **performance satisfaisante**, nettement supérieure à un
modèle aléatoire.

---

## 6. Conclusion et perspectives

Ce projet a montré que les techniques de machine learning peuvent être efficacement
utilisées pour analyser et estimer les prix immobiliers.
La surface habitable apparaît comme le facteur le plus déterminant du prix des maisons.

Les limites du modèle résident principalement dans l’utilisation d’un nombre restreint de
variables explicatives. Des améliorations futures pourraient inclure :
- l’intégration de davantage de variables,
- l’utilisation de modèles plus complexes,
- l’optimisation des hyperparamètres,
- une validation croisée plus avancée.

Ce travail constitue une base solide pour des analyses immobilières plus approfondies.
