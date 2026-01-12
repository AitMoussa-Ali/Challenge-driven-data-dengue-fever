# Final Project – Dengue Fever Prediction using Machine Learning & Neural Networks

## Description du projet

Ce projet consiste à développer et comparer plusieurs modèles de **Machine Learning** et de **Réseaux de Neurones** afin de prédire le nombre de cas de dengue dans deux villes distinctes (**San Juan (sj)** et **Iquitos (iq)**).  
Le travail couvre l’ensemble du pipeline de data science : **chargement des données, nettoyage, feature engineering, entraînement des modèles, évaluation et comparaison des performances**.

Le projet a été réalisé sous forme de notebook Python, avec une approche expérimentale et analytique.

---

## Structure du projet

- `code.ipynb` : Notebook principal contenant tout le pipeline du projet  
- `README.md` : Description du projet et instructions
- `Data` : Dataset
- `Figures` : figures analytiques

---

## Technologies et bibliothèques utilisées

- **Python**
- **Pandas** : manipulation et nettoyage des données  
- **NumPy** : calcul numérique  
- **Matplotlib** : visualisation des données  
- **Scikit-learn** :
  - Régression linéaire
  - Random Forest Regressor
  - Gradient Boosting
  - MLPRegressor
  - PCA
  - Cross-validation
- **PyTorch** :
  - Création de réseaux de neurones personnalisés
  - DataLoader
  - Fonctions de perte et optimisation

---

## Chargement des données

Les données sont importées depuis des fichiers CSV et chargées dans des **DataFrames Pandas**.  
Elles contiennent des informations climatiques, temporelles et géographiques utilisées pour prédire le nombre de cas de dengue.

---

## Prétraitement et nettoyage des données

### 1. Gestion des valeurs manquantes
- remplacement des valeurs manquantes
- Vérification de la cohérence des données

### 2. Encodage de la variable temporelle
La colonne `week_start_date` est transformée en plusieurs variables :
- Année
- Mois
- Jour

Cette approche permet de conserver l’information temporelle tout en la rendant exploitable par les modèles.

### 3. Encodage de la ville
- Utilisation du **One-Hot Encoding** pour la variable `city`
- Séparation des données en deux sous-ensembles :
  - **San Juan (sj)**
  - **Iquitos (iq)**

### 4. Séparation des features et des labels
- `X` : variables explicatives
- `y` : nombre de cas de dengue (variable cible)

---

## Analyse exploratoire des données

- Visualisation de la distribution des villes (diagramme circulaire)
- Analyse statistique des variables
- Compréhension de l’impact des facteurs climatiques

---

## Modèles utilisés

###  Modèles classiques de Machine Learning
- XGBoost
- Random Forest Regressor
- Gradient Boosting Regressor

Chaque modèle est :
- entraîné séparément pour chaque ville
- évalué avec une **cross-validation**
- analysé via une **fonction de perte**
- Metriques R^2 et MAE
- GridSearch

---

### Réseaux de neurones (MLP)

- **MLPRegressor (Scikit-learn)**
- Entraînement avec et sans **PCA**
- Comparaison des performances, avec Cross validation et GridSearch pour les parametres.

---

### Réseaux de neurones avec PyTorch

- Création d’un réseau de neurones personnalisé
- Implémentation de :
  - DataLoader
  - Boucle d’entraînement
  - Fonction de perte
  - Optimiseur
- Entraînement séparé pour chaque ville
- Application de la **cross-validation** et GridSearch

---

## Réduction de dimension – PCA

L’**Analyse en Composantes Principales (PCA)** est utilisée pour :
- réduire la dimension des données
- améliorer la stabilité de l’entraînement
- comparer les performances avec et sans réduction de dimension

---

## Résultats et comparaison

- Analyse comparative des performances de chaque modèle
- Comparaison entre :
  - modèles classiques
  - réseaux de neurones
  - modèles avec et sans PCA
- Étude séparée pour chaque ville (sj et iq)

---

## Conclusion

Ce projet montre que :
- Les performances varient selon la ville et le modèle utilisé
- Les réseaux de neurones offrent de bons résultats lorsque les données sont bien préparées
- Le PCA peut améliorer la stabilité mais pas toujours la performance finale
- Une approche par ville est plus efficace qu’un modèle global

---

## Améliorations possibles

- Ajout de modèles plus avancés (LSTM, GRU)
- Feature engineering plus poussé
- Optimisation des hyperparamètres
- Intégration d’un pipeline automatisé

---

## 👤 Auteur

Projet réalisé dans le cadre d’un **projet académique en Machine Learning / Data Science**.

