# Project Paper Approval Request

**National University of Computer & Emerging Sciences (Chiniot-Faisalabad Campus)**  
**Course:** CL3001 – Machine Learning Lab (Spring 2026)  
**Student Name:** Musa Rashid  
**Instructor:** Ms. Esha Iftikhar  
**Date:** October 29, 2026  

---

### 1. Selected Paper
* **Title:** Performance Evaluation of Machine Learning and Deep Learning Models for Credit Risk Prediction
* **Authors:** Irvine Mapfumo and Thokozani Shongwe
* **Venue & Date:** *Journal of Risk and Financial Management* (MDPI), Vol. 19, Issue 3, March 2026
* **Paper Link:** https://doi.org/10.3390/jrfm19030210

### 2. Datasets
* **Taiwanese Credit Card Default Dataset (UCI Repository):**  
  https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients  
  30,000 client records with 24 financial and repayment features (22.1% default rate).
* **Statlog German Credit Dataset (UCI Repository):**  
  https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data  
  1,000 loan applicant records with 20 credit and demographic features (30.0% default rate).

### 3. Reason for Choosing This Paper
I chose this paper because credit risk assessment is a practical problem in finance and the study compares core machine learning models covered in our course (Logistic Regression, Decision Tree, SVM, Random Forest, AdaBoost, XGBoost, and MLP) using 10-fold cross-validation. Both datasets are publicly available on the UCI repository and small enough to train and test thoroughly on standard hardware.

The paper also reports clear numerical baselines using SMOTE and SMOTE-ENN resampling (82.1% accuracy and 0.789 F1 on the Taiwanese dataset; 95.4% accuracy and 0.928 F1 on the German dataset). During replication, I plan to investigate how applying SMOTE-ENN before vs. inside cross-validation folds affects accuracy and probability calibration, and test whether probability calibration with cost-sensitive thresholding improves default risk estimation.
