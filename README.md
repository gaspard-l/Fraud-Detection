# Fraud Detection – Machine Learning Project
## Contexte

Ce projet a pour objectif de détecter des transactions frauduleuses à partir d’un dataset fortement déséquilibré.

La problématique est que :

- Les fraudes sont très rares

- Le coût d’un faux négatif (fraude non détectée) est élevé

- Trop de faux positifs dégradent l’expérience client

L’objectif n’est donc pas seulement d’optimiser l’accuracy, mais de trouver un équilibre pertinent entre recall et precision.

---

## Dataset
- Source : Kaggle Credit Card Fraud Detection
- Nombre de transactions : 284 807
- Fraudes : 492 (0.17%)

---

## Structure du Notebook
Le projet est organisé en trois grandes parties :

### Préparation des données
- Importation des bibliothèques
- Chargement du dataset
- Affichage de la forme générale et des premières lignes
- Analyse du déséquilibre des classes
- Séparation Train / Test
- Normalisation des variables numériques via un pipeline
La séparation train/test est effectuée avant la normalisation afin d’éviter toute fuite de données (data leakage).

### Premier modèle
Étapes :
- Création et entraînement du modèle
- Prédictions probabilistes
- Test d’un seuil initial à 0.3
- Étude des métriques :
    - Accuracy
    - Precision
    - Recall
    - F1-score
    - AUC
- Visualisation graphique pour déterminer le seuil optima
- Recherche du seuil maximisant le F1-score
- Analyse des variables les plus influentes
- Matrice de confusion

Objectif :
Maximiser la détection des fraudes tout en limitant les faux positifs.

### Deuxième modèle
Même méthodologie :
- Entraînement
- Optimisation du seuil
- Comparaison des métriques
- Matrice de confusion
Une comparaison claire est réalisée afin d’identifier le modèle offrant le meilleur compromis métier.

---

## Gestion du déséquilibre
Le dataset étant fortement déséquilibré, l’évaluation repose principalement sur :
- Recall
- F1-score
- Matrice de confusion
- AUC
Des techniques comme utilisée des poids (class_weight) pourraient être testées en amélioration future.

---

## Choix Méthodologiques
Le seuil de classification n’est pas laissé à 0.5 par défaut. \
Il est optimisé afin de :
- Réduire les faux négatifs (fraudes non détectées)
- Maintenir un taux acceptable de faux positifs
Ce choix reflète une approche orientée enjeu métier plutôt que purement statistique.

---

## Résultats
Une comparaison finale met en évidence :
- Le modèle le plus performant
- Le compromis recall / precision
- L’impact du choix du seuil
Le modèle retenu est celui offrant le meilleur équilibre pour un contexte de fraude bancaire.

---

## Bibliothèques
Projet développé en Python avec :
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## Installation
#### Cloner le repository
```bash
git clone https://github.com/gaspard-l/Fraud-Detection.git
cd Fraud-Detection
```
### Environnement (recommandé : Anaconda)
```bash
conda create -n fraud_env
conda activate fraud_env
conda install -r requirements.txt
```
### Alternative : environnement virtuel standard
```bash
python -m venv venv
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate     # Windows
pip install -r requirements.txt
```

## Exécution
```bash
jupyter notebook
fraud_detection.ipynb
```
---

## Améliorations possibles
- Optimisation des hyperparamètres
- Déploiement API (Flask / FastAPI)
- Monitoring des performances dans le temps

---

## Licence
Ce projet est libre d’utilisation et de modification.

---

## Auteur

Gaspard Lesourd
