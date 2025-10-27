🧠 TP2 — Advanced Regression & MLOps

ENSPY — Département Génie Informatique
Auteurs : [H. J. Mbolang]
 
🎯 Objectifs du TP

Ce projet illustre les principales étapes d’un pipeline de Machine Learning supervisé appliqué à un problème de régression (jeu de données Diabetes).
Il met l’accent sur :

Le compromis Biais / Variance

Les méthodes de régularisation (Ridge & LASSO)

Le suivi des expériences avec MLflow

Le déploiement et packaging du modèle (Joblib, Docker, API Flask)

⚙️ Structure du projet
TP2_Regression/
│
├── notebooks/
│   └── TP2_Regression.ipynb           # Notebook principal d'analyse et de modélisation
│
├── models/
│   ├── lasso_model.pkl                # Modèle final sauvegardé
│   └── scaler.pkl                     # StandardScaler associé
│
├── src/
│   └── app.py                         # Mini API Flask pour servir le modèle
│
├── requirements.txt                   # Dépendances Python
├── Dockerfile                         # Conteneurisation du projet
├── README.md                          # Documentation du projet
└── .gitignore

🧩 Contenu principal
1️⃣ Modélisation

Jeu de données : sklearn.datasets.load_diabetes

Modèles testés :

Régression linéaire (OLS)

Ridge Regression

LASSO Regression

Évaluation :

RMSE, R²

Validation croisée

Analyse de la sparsity (zéro de coefficients LASSO)

2️⃣ MLOps

MLflow pour le suivi automatique des modèles (paramètres, métriques, artefacts)

Joblib pour la sérialisation du scaler et du modèle

Docker pour la reproductibilité et le déploiement

Flask pour exposer le modèle via une API REST simple

🚀 Exécution locale
Installation des dépendances :
pip install -r requirements.txt

Lancer le notebook :
jupyter notebook notebooks/TP2_Regression.ipynb

Lancer le serveur Flask :
python src/app.py


Le modèle est alors accessible sur :

http://127.0.0.1:5000/predict

🧪 Tracking MLflow

Lancer le serveur MLflow :

mlflow ui


Puis ouvrir :
👉 http://127.0.0.1:5000

🐳 Conteneurisation (Docker)

Construction de l’image :

docker build -t tp2_regression_app .


Exécution du conteneur :

docker run -p 5000:5000 tp2_regression_app

📊 Résultats attendus
Modèle	RMSE (test)	R² (test)	Commentaire
OLS	~49.0	~0.58	Baseline linéaire
Ridge	~48.3	~0.59	Légère amélioration
LASSO	~45.2	~0.61	Meilleur compromis Sparsity/Performance
📦 Dépendances principales

Python ≥ 3.9

numpy, pandas, scikit-learn

joblib, mlflow

flask (ou fastapi)

matplotlib, seaborn

🧠 Concepts abordés

Biais vs Variance

Régularisation (L1, L2)

Sélection de caractéristiques par LASSO

MLOps : traçabilité, reproductibilité, déploiement

👨‍💻 Auteur: H. J. Mbolang

Projet réalisé dans le cadre du TP2 — Advanced Regression & MLOps

HJM, 2025