# Détection de Fraude par Carte de Crédit avec Régression Logistique

Ce projet effectue une analyse de détection de fraude par carte de crédit en utilisant la régression logistique. Il inclut des étapes de prétraitement des données, d'entraînement de modèle, d'évaluation et de sauvegarde du modèle.

## Prérequis

* Python 3.x
* Bibliothèques Python :
  * `numpy`
  * `pandas`
  * `matplotlib`
  * `seaborn`
  * `scikit-learn`
  * `joblib`

Vous pouvez installer les bibliothèques nécessaires en utilisant pip :

```bash
pip install numpy pandas matplotlib seaborn scikit-learn joblib
```

## Etapes

1. **Chargement et Exploration des Données :**
    * Charge le jeu de données `creditcard.csv` à l'aide de pandas.
    * Affiche les premières lignes et les statistiques descriptives des données.
    * Sépare les transactions frauduleuses et non frauduleuses.
    * Affiche le nombre de transactions frauduleuses et non frauduleuses.
    * Visualise la distribution des transactions frauduleuses et non frauduleuses par rapport au montant.
    * Affiche une matrice de corrélation pour comprendre les relations entre les caractéristiques.

2. **Préparation des Données :**
    * Divise les données en ensembles d'entraînement et de test (30% pour le test).
    * Calcule et affiche le nombre de transactions frauduleuses dans les ensembles d'entraînement et de test.
    * Supprime la colonne de la variable cible (Class) du jeu de données X.

3. **Régression Logistique (Données Déséquilibrées) :**
    * Entraîne un modèle de régression logistique sur les données d'entraînement non mises à l'échelle.
    * Évalue le modèle sur l'ensemble de test et affiche le score, le rapport de classification et la matrice de confusion.

4. **Régression Logistique (Poids de Classe Équilibrés et GridSearchCV) :**
    * Met à l'échelle les données d'entraînement et de test à l'aide de `StandardScaler`.
    * Effectue une recherche par grille (`GridSearchCV`) pour trouver les meilleurs hyperparamètres (`C`) pour un modèle de régression logistique avec des poids de classe équilibrés.
    * Entraîne le modèle avec les meilleurs paramètres trouvés.
    * Évalue le modèle sur l'ensemble de test et affiche les meilleurs paramètres, le score, le rapport de classification et la matrice de confusion.

5. **Sauvegarde du Modèle et du Scaler :**
    * Sauvegarde le modèle de régression logistique entraîné et le scaler à l'aide de `joblib`
