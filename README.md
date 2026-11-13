# SDD Mini-Hackathon 2025 — Heart-Risk Classification

Team experiments for the SUPAERO SDD mini-hackathon, exploring a binary heart-risk prediction task on tabular data.

## What is included

The notebooks explore class imbalance, preprocessing and several classifiers, including Random Forest, XGBoost and CatBoost. Ali's notebooks include missing-value handling, resampling experiments, Optuna hyperparameter search and decision-threshold tuning.

Start with [ali.ipynb](ali.ipynb) for the earlier exploration and [ali_V2.ipynb](ali_V2.ipynb) for the CatBoost/Optuna extension. The latter combines training and extra data, creates a stratified validation split, tunes CatBoost with an F1 objective and exports predictions. These are experimental notebooks; saved scores should not be treated as an unbiased final test benchmark.

## Repository map

- `ali.ipynb`, `ali_V2.ipynb` — Ali's experiment notebooks.
- `alexandre.ipynb`, `francois.ipynb` — additional team notebook files; completeness varies.
- `data/` — train, test, extra data and a sample submission.
- `models/` — serialized model versions.
- `parameters/` — saved CatBoost configurations.
- `submissions/` — prediction CSVs from different experiments.
- `catboost_info/` — generated training logs.

## Running the experiments

Install Git LFS before cloning. On Debian/Ubuntu:

```bash
sudo apt install git-lfs
git lfs install
git clone https://github.com/ali-hou-supaero/sdd-hackaton-25-heart-risk.git
cd sdd-hackaton-25-heart-risk
git lfs pull
```

On other systems, install Git LFS with the appropriate installer and initialize it with `git lfs install`.

Use Jupyter with Python, pandas, NumPy, matplotlib, seaborn, SciPy, scikit-learn, imbalanced-learn, XGBoost, CatBoost, Optuna and joblib. Ali's second notebook also imports Optuna's CatBoost integration. No version-pinned environment is provided.

Run notebooks from the repository root so paths such as `data/train.csv` resolve correctly. Review training and export cells before execution: they can take substantial time and overwrite model, parameter and submission files. In particular, `ali_V2.ipynb` configures a 300-trial study. Only load trusted serialized models.

## Scope and attribution

This is a collaborative academic hackathon project. Notebook names help locate individual work but do not establish exclusive ownership of the overall pipeline. This README does not claim a leaderboard ranking or independently verified score.

The models are educational experiments, not a clinically validated diagnostic system. Data usage and redistribution terms must be checked with the original hackathon source before reuse.
