# Mini-hackathon SDD 2025 — Classification du risque cardiaque

Expériences d’équipe pour le mini-hackathon SDD de SUPAERO, consacrées à une tâche de prédiction binaire du risque cardiaque sur des données tabulaires.

## Contenu des expériences

Les notebooks explorent le déséquilibre des classes, le prétraitement et plusieurs classifieurs, dont Random Forest, XGBoost et CatBoost. Les notebooks d’Ali incluent le traitement des valeurs manquantes, des expériences de rééchantillonnage, la recherche d’hyperparamètres avec Optuna et l’ajustement du seuil de décision.

Commencer par [ali.ipynb](ali.ipynb) pour l’exploration initiale et [ali_V2.ipynb](ali_V2.ipynb) pour l’extension CatBoost/Optuna. Cette dernière combine les données d’entraînement et les données supplémentaires, crée une séparation stratifiée de validation, optimise CatBoost selon le F1 et exporte les prédictions. Ces notebooks sont expérimentaux ; les scores enregistrés ne constituent pas une évaluation finale non biaisée sur un jeu de test.

## Organisation du dépôt

- `ali.ipynb`, `ali_V2.ipynb` — notebooks d’expériences d’Ali.
- `alexandre.ipynb`, `francois.ipynb` — autres fichiers notebooks de l’équipe, dont le degré d’avancement varie.
- `data/` — données d’entraînement, de test, supplémentaires et exemple de soumission.
- `models/` — versions des modèles sérialisés.
- `parameters/` — configurations CatBoost enregistrées.
- `submissions/` — fichiers CSV de prédictions issus des expériences.
- `catboost_info/` — journaux d’entraînement générés.

## Exécution des expériences

Installer Git LFS avant de cloner. Sous Debian/Ubuntu :

```bash
sudo apt install git-lfs
git lfs install
git clone https://github.com/ali-hou-supaero/sdd-hackaton-25-heart-risk.git
cd sdd-hackaton-25-heart-risk
git lfs pull
```

Sur les autres systèmes, installer Git LFS avec l’installateur adapté et l’initialiser avec `git lfs install`.

Utiliser Jupyter avec Python, pandas, NumPy, matplotlib, seaborn, SciPy, scikit-learn, imbalanced-learn, XGBoost, CatBoost, Optuna et joblib. Le second notebook d’Ali importe également l’intégration CatBoost d’Optuna. Aucun environnement aux versions verrouillées n’est fourni.

Exécuter les notebooks depuis la racine du dépôt pour résoudre correctement les chemins comme `data/train.csv`. Vérifier les cellules d’entraînement et d’export avant exécution : elles peuvent prendre beaucoup de temps et écraser des modèles, des paramètres ou des soumissions. En particulier, `ali_V2.ipynb` configure une étude de 300 essais. Charger uniquement des modèles sérialisés de confiance.

## Périmètre et attribution

Il s’agit d’un projet collectif de hackathon académique. Les noms des notebooks facilitent le repérage du travail individuel, sans établir une attribution exclusive de l’ensemble du pipeline. Ce README ne revendique ni classement dans la compétition ni score vérifié indépendamment.

Les modèles sont des expériences pédagogiques, pas un système de diagnostic cliniquement validé. Les conditions d’utilisation et de redistribution des données doivent être vérifiées auprès de la source originale du hackathon avant réutilisation.
