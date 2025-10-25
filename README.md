# Prédiction du Risque Obstétrique - Projet Data Science

Projet académique réalisé en sciences des données visant à prédire le niveau de risque de grossesse chez des femmes diabétiques.

## Objectif

L'objectif était d'analyser un jeu de données médicales (âge, tension, glycémie, etc.) pour développer deux types de classifieurs :

1.  **Binaire** : Prédire "risque" (classes 1 et 2) vs "sans risque" (classe 0).
2.  **Multi-classe** : Prédire les 3 niveaux de risque (faible, moyen, élevé).

La métrique d'évaluation principale utilisée est la **Précision Équilibrée (Balanced Accuracy)**.

## Démarche et Modèles

L'analyse complète, l'entraînement des modèles et la sélection des hyperparamètres (via `GridSearchCV`) se trouvent dans le notebook Jupyter.

### Classification Binaire (Risque vs Sans Risque)

Comparaison de trois modèles sur les données normalisées avec et sans PCA :

* **Régression Logistique (L2)** : BA = 0.61
* **K-Plus Proches Voisins (KNN)** : BA = 0.75 (pour K=22)
* **Random Forest** : **BA = 0.80 (pour n=120)**

Le **Random Forest** a été retenu comme classifieur final et a obtenu une précision équilibrée de **0.80** sur le jeu de test.

### Classification Multi-classe (Niveaux 0, 1, 2)

Un classifieur **KNN** a été optimisé (K=12) et a atteint une précision équilibrée de **0.73** sur le jeu de test. L'analyse de la matrice de confusion a montré une bonne détection des risques élevés, mais des difficultés à distinguer les risques faibles et moyens.

## Technologies Utilisées

* Python
* Pandas & Numpy
* Scikit-learn
* Matplotlib & Seaborn

---
