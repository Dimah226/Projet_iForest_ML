# Détection de fraude automobile par Isolation Forest

Projet de M2 Actuariat appliquant l'article de Liu, Ting et Zhou (2012) au jeu public `carclaims`.

**Membres :** ROBGO Hamid, DIAKITE Sekou Fadel, KOFFI Daphne et KANTE Karifala.  
**Dépôt :** https://github.com/Dimah226/Projet_iForest_ML

## Exécution

```powershell
python -m venv .venv
.venv\Scripts\python -m pip install -r requirements.txt
.venv\Scripts\python -m jupyter notebook
```

Exécuter dans l'ordre :

1. `notebooks/01_eda_carclaims.ipynb`
2. `notebooks/02_feature_engineering.ipynb`
3. `notebooks/03_modeling.ipynb`

## Structure

- `data/raw/fraud_oracle.csv` : données brutes, jamais modifiées.
- `data/sorties/` : quatre CSV finaux reproductibles et leur README.
- `notebooks/` : EDA, préparation et expérimentation.
- `rapport/` : source LaTeX, bibliographie BibTeX, figures et `make_figures.py` (régénère les figures).
- `output/pdf/rapport_isolation_forest_latex.pdf` : rapport compilé (6 pages A4).
- `Ennoncer/` : article de référence et consignes.

## Protocole

La cible `FraudFound_P` n'est jamais fournie aux détecteurs. Les transformations sont ajustées sur le train. Les hyperparamètres sont choisis sur une validation interne; le test final n'est consulté qu'une fois.

## Données

Le jeu `Vehicle Insurance Claim Fraud Detection` comporte 15 420 déclarations, 33 variables et 923 fraudes (5,99 %). Source : Kaggle, jeu `shivamb/vehicle-claim-fraud-detection`, issu d'Angoss Knowledge Seeker. Vérifier les conditions de diffusion Kaggle avant redistribution publique du CSV.

## Résultat attendu

Le projet évalue honnêtement si les fraudes sont des anomalies globales au sens d'Isolation Forest. Des performances proches de l'aléatoire constituent un résultat scientifique à analyser, pas à masquer.
