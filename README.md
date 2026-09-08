# 🎓 Student Performance Prediction

Prédiction de la réussite (Pass/Fail) d'étudiants à partir de données académiques et comportementales, à l'aide de modèles de Machine Learning classiques.

## 📋 Description

Ce projet met en œuvre un pipeline complet de classification binaire :
- **Nettoyage des données** (valeurs manquantes, doublons)
- **Encodage** des variables catégorielles
- **Rééquilibrage des classes** avec SMOTE
- **Entraînement** de trois modèles : Régression Logistique, Arbre de Décision, Random Forest
- **Évaluation comparative** (Accuracy, Precision, Recall, F1-score, Log Loss, ROC AUC)

## 📁 Structure du projet

```
.
├── student_performance_prediction.ipynb   # Notebook principal
├── data/                                  # Jeu de données (non versionné, voir ci-dessous)
├── requirements.txt                       # Dépendances Python
├── .gitignore
└── README.md
```

## 📊 Données

Le notebook attend un fichier `student_performance_2000.csv` (à placer dans `data/` ou à la racine, selon votre organisation) contenant notamment les colonnes suivantes :
- `attendance_percent`
- `previous_grade`
- `internet_access` (Yes/No)
- `extracurricular_activity` (Yes/No)
- `result` (Pass/Fail) — variable cible

> ⚠️ Le fichier de données n'est pas inclus dans ce dépôt. Ajoutez le vôtre dans `data/` avant d'exécuter le notebook, ou adaptez le chemin dans la première cellule de chargement.

## 🚀 Installation

```bash
git clone https://github.com/<votre-utilisateur>/<nom-du-repo>.git
cd <nom-du-repo>
python -m venv venv
source venv/bin/activate  # Windows : venv\Scripts\activate
pip install -r requirements.txt
```

## ▶️ Utilisation

```bash
jupyter notebook student_performance_prediction.ipynb
```

Exécutez les cellules dans l'ordre. Le notebook :
1. Charge et nettoie les données
2. Encode les variables catégorielles
3. Sépare train/test (80/20, stratifié)
4. Applique SMOTE sur le jeu d'entraînement pour rééquilibrer les classes
5. Entraîne 3 modèles et affiche leurs métriques comparées

## 🧠 Modèles évalués

| Modèle | Bibliothèque |
|---|---|
| Régression Logistique | `sklearn.linear_model.LogisticRegression` |
| Arbre de Décision | `sklearn.tree.DecisionTreeClassifier` |
| Random Forest | `sklearn.ensemble.RandomForestClassifier` |

## 🛠️ Stack technique

- Python 3
- pandas, numpy
- scikit-learn
- imbalanced-learn (SMOTE)
- matplotlib, seaborn

## 📈 Améliorations possibles

- Validation croisée (cross-validation) au lieu d'un simple split train/test
- Recherche d'hyperparamètres (GridSearchCV / RandomizedSearchCV)
- Ajout d'autres modèles (XGBoost, LightGBM)
- Analyse de l'importance des features
- Suivi d'expérimentation (MLflow, Weights & Biases)

## 📄 Licence

Ce projet est distribué sous licence MIT — voir le fichier [LICENSE](LICENSE).
