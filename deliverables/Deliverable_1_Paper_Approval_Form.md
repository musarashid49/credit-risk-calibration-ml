# Deliverable 1: Research Paper Approval Form

**Course:** CL3001 — Machine Learning Lab (Spring 2026)  
**University:** National University of Computer & Emerging Sciences (FAST-NUCES), Chiniot-Faisalabad Campus  
**Instructor:** Esha Iftikhar  
**Student Name:** Musa Rashid  
**Submission Date:** October 2026  

---

## 1. Selected Research Paper Details

* **Paper Title:** *Performance Evaluation of Machine Learning and Deep Learning Models for Credit Risk Prediction*
* **Authors:** Irvine Mapfumo and Thokozani Shongwe (Department of Electrical and Electronic Engineering Science, University of Johannesburg)
* **Journal / Venue:** *Journal of Risk and Financial Management* (MDPI), Vol. 19, Issue 3, Article 210
* **Publication Date:** March 2026 (2026 Peer-Reviewed Journal Publication)
* **Paper Link / DOI:** [https://doi.org/10.3390/jrfm19030210](https://doi.org/10.3390/jrfm19030210)
* **Application Domain:** Finance & FinTech (Automated Credit Risk Underwriting & Default Prediction)

---

## 2. Publicly Available Datasets Used

The selected paper evaluates its methodology on two standard, publicly available benchmark datasets from the **UCI Machine Learning Repository** (also hosted on Kaggle):

1. **Taiwanese Credit Card Default Dataset**
   * **Link:** [https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients)
   * **Size & Structure:** 30,000 client records, 24 financial and repayment history attributes (including credit limit `LIMIT_BAL`, demographics, 6 months of repayment status `PAY_0`–`PAY_6`, bill statements, and previous payments).
   * **Class Distribution:** Imbalanced binary classification — 77.88% Non-Default (`0`) vs. 22.12% Default (`1`).
2. **Statlog (German Credit Data) Dataset**
   * **Link:** [https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data](https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data)
   * **Size & Structure:** 1,000 loan applicant records, 20 financial and demographic attributes (checking account status, loan duration, credit history, credit amount, employment stability).
   * **Class Distribution:** Imbalanced binary classification — 70.0% Good Credit Risk vs. 30.0% Bad Credit Risk (Default).

---

## 3. Alignment with CL3001 Course Topics & Methodology

This paper directly implements core machine learning techniques taught in **CL3001**:
* **Data Pre-Processing & Imbalance Handling:** Standard scaling, categorical encoding, and resampling techniques including **SMOTE** (Synthetic Minority Over-sampling Technique), **ENN** (Edited Nearest Neighbors), and hybrid **SMOTE-ENN**.
* **Supervised Classification Algorithms:**
  * Logistic Regression (LR)
  * Decision Tree (DT)
  * Support Vector Machine (SVM)
  * Random Forest (RF)
  * Boosting Ensembles (AdaBoost & XGBoost)
  * Multilayer Perceptron (MLP / Neural Network)
* **Evaluation Protocol & Metrics:** 10-fold stratified cross-validation reporting **Accuracy, Precision, Recall, F1-Score, and ROC-AUC** (e.g., achieving **95.4% Accuracy / 0.928 F1** with MLP + SMOTE-ENN on German Credit, and **82.1% Accuracy / 0.789 F1** with Random Forest + SMOTE-ENN on Taiwanese Credit).

---

## 4. Reason for Selection & Planned Research Contribution (Step 6 & Step 7)

1. **High Real-World Impact:** Credit default prediction is the foundational engine of modern banking and AI-native financial underwriting.
2. **Full Reproducibility on Standard Compute:** Both datasets (1,000 and 30,000 tabular records) can be trained and evaluated across multiple random seeds and 10-fold cross-validation within minutes on CPU / Google Colab.
3. **Identified Methodological Gap & Planned Improvement (Step 7 Bonus & Future Publication):**
   * **Leakage & Calibration Audit:** Many studies applying hybrid SMOTE-ENN achieve inflated accuracy (such as 95.4% on German Credit) when resampling is applied prior to cross-validation splitting, and resampling shifts the prior class probability—severely distorting predicted **Probability of Default ($PD$)** calibration required under Basel III banking regulations.
   * **Proposed Novel Extension:** In Step 7, we will (a) rigorously compare pre-split vs. strict in-fold SMOTE-ENN, (b) apply **Isotonic and Platt Probability Calibration** to restore true Probability of Default estimates (measured via Brier Score and Expected Calibration Error), and (c) introduce **Instance-Dependent Bayes Minimum Risk (Cost-Sensitive) Thresholding** using each borrower's actual credit limit (`LIMIT_BAL`) to minimize real financial portfolio loss.
