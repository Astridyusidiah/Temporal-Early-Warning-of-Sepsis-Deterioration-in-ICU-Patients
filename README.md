# Temporal Early Warning of Sepsis Deterioration in ICU Patients

## Overview
This repository presents a patient-level early warning system for predicting sepsis deterioration in intensive care unit (ICU) patients using longitudinal clinical data. The task is formulated as prospective risk prediction within a fixed future time horizon, rather than retrospective sepsis detection.

The project is intended as a research-oriented implementation aligned with PhD-level standards in health data science and clinical machine learning.

## Problem Formulation
At each ICU time point, the model estimates the probability that a patient will develop sepsis within the next H hours, given currently available clinical information. Predictions are evaluated at the patient level to avoid temporal and cross-patient data leakage.

## Methodological Pipeline
The analysis follows the steps below:

1. Data ingestion and structural inspection  
2. Temporal alignment and patient-level ordering  
3. Prospective early warning label construction  
4. Feature definition and cohort construction  
5. Patient-level train–test partitioning  
6. Missing-value imputation and feature preparation  
7. Gradient boosted tree model development  
8. Discriminative performance evaluation  
9. Global model interpretability analysis  
10. Local explanation of individual risk states  
11. Threshold-based clinical decision analysis (baseline)  
12. Clinical utility and risk stratification analysis  

## Model and Evaluation
A gradient boosted decision tree model (LightGBM) is trained using patient-level splits. Performance is assessed using AUROC and precision–recall metrics due to strong class imbalance.

Rather than relying on a single decision threshold, predicted risk scores are further evaluated through risk stratification to assess potential clinical utility for prioritization and early intervention.

## Key results
- Global feature importance (SHAP bar):  
  [`figures/shap_global_bar.png`](figures/shap_global_bar.png)

- Global SHAP distribution (beeswarm):  
  [`figures/shap_global_beeswarm.png`](figures/shap_global_beeswarm.png)

- Local explanation (highest-risk patient):  
  [`figures/shap_local_highest_risk.png`](figures/shap_local_highest_risk.png)


## Repository Structure
- `notebooks/` — full analysis pipeline  
- `figures/` — key evaluation and interpretability figures  
- `README.md` — project overview and methodology  

## Disclaimer
This project is intended for research and educational purposes only and does not constitute a clinical decision support system.
