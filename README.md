# Transaction Fraud Detection System

## Project Background

This project is a portfolio-oriented fraud detection and risk control system. V1 focuses only on financial transaction fraud detection using the PaySim dataset.

The V1 goal is to build a practical financial fraud detection pipeline that combines supervised machine learning with a supplementary deep learning anomaly detection module. Integrated risk scoring will be developed after both the supervised model and Autoencoder module are available.

E-commerce transaction fraud detection is future work and is not implemented in V1.

## V1 Scenario

Financial transaction fraud detection using PaySim:

- Detect suspicious simulated mobile money transactions.
- Analyze transaction amount, transaction type, account balance changes, and fraud labels.
- Generate fraud probability, anomaly score, final risk score, risk level, and recommended action.

## V1 Technical Pipeline

```text
PaySim data
-> EDA
-> feature engineering
-> train Logistic Regression, Random Forest, and XGBoost
-> compare supervised baseline models
-> tune candidate supervised models and select the final supervised model
-> train Autoencoder as a supplementary anomaly detection module
-> generate fraud probability, anomaly score, risk score, risk level, and recommended action
-> display results in a local Streamlit dashboard
```

## V1 Project Structure

```text
transaction-fraud-detection-system/
|-- app/
|   `-- streamlit_app.py
|-- data/
|   |-- raw/
|   |   `-- financial/
|   `-- processed/
|       `-- financial/
|-- models/
|   |-- ml/
|   `-- autoencoder/
|-- notebooks/
|   |-- 01_financial_eda.ipynb
|   |-- 02_financial_ml_baseline.ipynb
|   |-- 03_financial_ml_tuning_and_model_selection.ipynb
|   |-- 04_financial_autoencoder_experiment.ipynb
|   `-- 05_financial_risk_scoring_and_dashboard_prep.ipynb
|-- reports/
|   `-- results.md
|-- src/
|   |-- __init__.py
|   |-- check_environment.py
|   |-- preprocessing.py
|   |-- train_ml.py
|   |-- train_autoencoder.py
|   |-- model.py
|   |-- evaluate.py
|   |-- model_selection.py
|   |-- risk_scoring.py
|   `-- predict.py
|-- README.md
|-- requirements.txt
`-- .gitignore
```

## Folder and File Roles

- `data/raw/financial/`: stores the original PaySim dataset.
- `data/processed/financial/`: stores cleaned and feature-engineered PaySim data.
- `notebooks/01_financial_eda.ipynb`: explores PaySim data quality, fraud labels, transaction types, and class imbalance.
- `notebooks/02_financial_ml_baseline.ipynb`: compares Logistic Regression, Random Forest, and XGBoost supervised baselines.
- `notebooks/03_financial_ml_tuning_and_model_selection.ipynb`: tunes supervised candidate models and selects the final supervised ML model.
- `notebooks/04_financial_autoencoder_experiment.ipynb`: experiments with the supplementary PyTorch Autoencoder anomaly detection module.
- `notebooks/05_financial_risk_scoring_and_dashboard_prep.ipynb`: combines supervised fraud probability, Autoencoder anomaly signals, and business rules for risk scoring and dashboard preparation.
- `src/preprocessing.py`: reusable PaySim loading, cleaning, encoding, scaling, and splitting utilities.
- `src/train_ml.py`: future training entry point for Logistic Regression, Random Forest, and XGBoost.
- `src/train_autoencoder.py`: future training entry point for the autoencoder anomaly detector.
- `src/model.py`: future PyTorch autoencoder model definition.
- `src/evaluate.py`: reusable evaluation metrics and threshold analysis helpers.
- `src/model_selection.py`: model comparison and best-model selection utilities.
- `src/risk_scoring.py`: converts fraud probability and anomaly score into risk score, risk level, and recommended action.
- `src/predict.py`: future prediction utilities for new transactions.
- `src/check_environment.py`: simple environment verification script.
- `app/streamlit_app.py`: future local Streamlit dashboard.
- `models/ml/`: future saved supervised ML models and preprocessing artifacts.
- `models/autoencoder/`: future saved autoencoder model and anomaly threshold metadata.
- `reports/results.md`: experiment plan, model comparison notes, and final result summary.

## Future Development Steps

1. Add the PaySim dataset manually to `data/raw/financial/`.
2. Perform financial EDA in `01_financial_eda.ipynb`.
3. Implement feature engineering in `src/preprocessing.py`.
4. Train Logistic Regression, Random Forest, and XGBoost baselines.
5. Compare supervised baseline models in `02_financial_ml_baseline.ipynb`.
6. Tune candidate supervised models and select the final supervised model in `03_financial_ml_tuning_and_model_selection.ipynb`.
7. Train the Autoencoder as a supplementary anomaly detector in `04_financial_autoencoder_experiment.ipynb`.
8. Build integrated risk scoring after both supervised ML and Autoencoder signals are available.
9. Prepare the local Streamlit dashboard workflow.
10. Record final metrics and findings in `reports/results.md`.
