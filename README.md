# Superconductor Critical Temperature Prediction

This project aims to predict the critical temperature (`critical_temp`) of superconductors based on a set of feature-engineered descriptors derived from the chemical formula. The workflow includes data preprocessing, exploratory data analysis (EDA), feature scaling, hyperparameter tuning with Optuna, model training (Random Forest, XGBoost, LightGBM, CatBoost), and experiment tracking with MLflow.

## Table of Contents
- [Installation](#installation)
- [Data](#data)
- [Usage](#usage)
- [Modeling Approach](#modeling-approach)
- [License](#license)

---
## Installation

Clone the repository and install the required Python packages.

```bash
git clone https://github.com/your-username/superconductor-tc-prediction.git
cd superconductor-tc-prediction
```

---
It is recommended to use a virtual environment.

```bash
# Create and activate a virtual environment (optional)
python -m venv venv
source venv/bin/activate   # On Windows use: venv\Scripts\activate
```
Install dependencies:

```bash
pip install -r requirements.txt
```
---
## Data
Place the required CSV files inside a data/ folder at the root of the project:

- train.csv – training set features.

- test.csv – test set features.

- formula_train.csv – chemical formula information for the training set.

- formula_test.csv – chemical formula information for the test set.

The notebook merges the feature data with formula-derived attributes before modeling.
---

##Usage
The main workflow is implemented in the Jupyter notebook SemiCondutorProblem.ipynb.

To run the notebook:

```bash
jupyter notebook SemiCondutorProblem.ipynb
```

## Execute the cells sequentially to perform:

- Library imports and data loading.

- Merging of feature data with formula descriptors.

- Exploratory Data Analysis (EDA) – summary statistics, visualizations.

- Preprocessing – scaling, handling missing values (if any).

- Hyperparameter optimization using Optuna for each model.

- Model training and evaluation (cross-validation, metrics).

- Experiment logging with MLflow (optional, requires MLflow server setup).

You can also convert the notebook to a Python script and run it:

```bash
jupyter nbconvert --to script SemiCondutorProblem.ipynb
python SemiCondutorProblem.py
```

## Modeling Approach
The notebook implements several regression models to predict critical_temp:

- Random Forest Regressor

- XGBoost Regressor

- LightGBM Regressor

- CatBoost Regressor

For each model, hyperparameter tuning is performed using Optuna with cross-validation. The models are evaluated using metrics such as RMSE, MAE, and R².

MLflow is used to track parameters, metrics, and artifacts; you can view the results by launching the MLflow UI:

```bash
mlflow ui
```
---
## License
This project is licensed under the MIT License
