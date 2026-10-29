# Calibrated & Cost-Sensitive Credit Risk Underwriting

**Replication, Methodological Audit, and Research Extension of Mapfumo & Shongwe (2026)**

[![Course](https://img.shields.io/badge/Course-CL3001_Machine_Learning_Lab-blue)]()
[![Base Paper](https://img.shields.io/badge/DOI-10.3390%2Fjrfm19030210-green)](https://doi.org/10.3390/jrfm19030210)
[![Domain](https://img.shields.io/badge/Domain-FinTech_%26_Credit_Risk-orange)]()

## Overview

This repository contains the complete experimental pipeline, replication study, methodological leakage audit, and novel research extension for **CL3001 Machine Learning Lab** and subsequent academic publication:

> **Base Paper Replicated:**  
> Mapfumo, I., & Shongwe, T. (2026). *Performance Evaluation of Machine Learning and Deep Learning Models for Credit Risk Prediction*. **Journal of Risk and Financial Management (MDPI)**, 19(3), 210. [https://doi.org/10.3390/jrfm19030210](https://doi.org/10.3390/jrfm19030210)

> **Our Novel Research Contribution:**  
> *"Beyond Resampled Accuracy: Leakage-Free Calibration and Instance-Dependent Cost-Sensitive Learning for Credit Risk Underwriting"*

---

## Core Research Contributions

1. **Empirical Audit of Hybrid Resampling (Pre-Fold vs. Strict In-Fold `SMOTE-ENN`):**
   * Replicates the base paper's benchmark across **Logistic Regression, Decision Tree, SVM, Random Forest, AdaBoost, XGBoost, and MLP** on the **UCI German Credit** (1,000 rows) and **UCI Taiwanese Credit Card Default** (30,000 rows) datasets.
   * Quantifies the exact inflation caused by pre-cross-validation hybrid resampling (`SMOTE-ENN`) versus leak-free in-fold pipeline execution.
2. **Post-Resampling Probability Calibration (Basel III / IFRS 9 Compliance):**
   * Demonstrates via **Reliability Diagrams**, **Brier Score**, and **Expected Calibration Error (ECE)** that hybrid oversampling/undersampling (`SMOTE-ENN`) severely distorts Probability of Default ($PD$) estimates.
   * Benchmarks **Analytical Prior-Shift Correction**, **Platt Scaling**, and **Isotonic Regression** to restore well-calibrated $PD$ predictions without sacrificing minority-class recall.
3. **Instance-Dependent Bayes Minimum Risk (BMR) Underwriting & SHAP Stability:**
   * Replaces static $\tau = 0.50$ classification thresholds with an instance-dependent economic decision rule incorporating individual borrower credit limits (`LIMIT_BAL`), Exposure at Default ($EAD$), and Loss Given Default ($LGD$).
   * Evaluates **SHAP Feature Importance Rank Stability** across resampling and calibration regimes.

---

## Repository Structure

```text
credit-risk-calibration-ml/
├── deliverables/
│   ├── Deliverable_1_Paper_Approval_Form.md
│   └── Deliverable_1_Paper_Approval_Form.pdf
├── data/                        # Automated UCI dataset download & caching
├── src/
│   ├── data_loader.py           # UCI German & Taiwanese dataset loaders & preprocessors
│   ├── replication_pipeline.py  # Step 4 & 5: Base paper replication (LR, DT, SVM, RF, AdaBoost, XGB, MLP)
│   ├── leakage_audit.py         # Step 6: Pre-CV vs. In-Fold SMOTE-ENN empirical comparison
│   ├── calibration_cost.py      # Step 7: Platt/Isotonic calibration & Instance-Dependent Bayes Risk
│   └── evaluate_metrics.py      # Multi-seed metrics, ECE, Brier Score, Expected Financial Savings
├── notebooks/                   # Interactive Jupyter/Colab notebooks for EDA & visual reports
├── results/                     # Generated tables, ROC/PR curves, reliability diagrams, SHAP plots
└── requirements.txt
```
