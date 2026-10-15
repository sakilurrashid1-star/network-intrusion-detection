# Machine Learning-Based Multiclass Network Intrusion Detection

**Author:** Alkamah Sakilur Rashid  
**Project area:** Data Science · Machine Learning · Cybersecurity  
**Status:** Research / portfolio project

## Overview

This project evaluates supervised machine-learning models for classifying network traffic into 12 classes, including benign traffic and multiple attack categories. Three models are compared: Logistic Regression, Random Forest, and XGBoost.

The prepared modeling dataset contains **210,736 records**, **70 predictive features**, and **12 target classes**.

## Key results

| Model | Accuracy | Macro Precision | Macro Recall | Macro F1 |
|---|---:|---:|---:|---:|
| Logistic Regression | 97.14% | 94.22% | 83.36% | 83.47% |
| Random Forest | 99.52% | 92.94% | 92.64% | **92.69%** |
| XGBoost | **99.57%** | 92.86% | 92.65% | 92.66% |

**Interpretation:** XGBoost achieved the highest overall accuracy, while Random Forest achieved the highest Macro F1-score. These metrics measure different aspects of performance, so the result should not be reduced to accuracy alone.

### Important limitation

Web Attack - XSS was the most difficult class for XGBoost:
- Precision: 43.75%
- Recall: 32.31%
- F1-score: 37.17%
- Correctly classified: 42 of 130 test examples
- 85 XSS examples were predicted as Web Attack - Brute Force

This is an important weakness and should be clearly disclosed in any presentation of the project.

## Project objectives

- Prepare network-traffic data for multiclass classification.
- Explore the distribution of the traffic classes.
- Compare Logistic Regression, Random Forest, and XGBoost.
- Evaluate accuracy and macro-averaged metrics.
- Analyze per-class performance and confusion patterns.
- Examine XGBoost feature importance.
- Identify limitations and propose future improvements.

## Dataset classes

`BENIGN`, `Bot`, `DDoS`, `DoS GoldenEye`, `DoS Hulk`, `DoS Slowhttptest`, `DoS slowloris`, `FTP-Patator`, `PortScan`, `SSH-Patator`, `Web Attack - Brute Force`, `Web Attack - XSS`.

## Repository structure

```text
network-intrusion-detection/
├── README.md
├── requirements.txt
├── LICENSE
├── notebooks/
│   └── network_intrusion_detection.ipynb   # Add your original Colab notebook
├── figures/
│   ├── class_distribution.png              # Add your saved figure
│   ├── model_comparison.png                # Add your saved figure
│   ├── confusion_matrix.png                # Add your saved figure
│   └── feature_importance.png              # Add your saved figure
├── report/
│   └── Machine_Learning_Based_Multiclass_Network_Intrusion_Detection_Report.pdf
├── data/
│   └── README.md
└── evidence/
    └── README.md
```

## Methodology summary

1. Inspect and prepare the dataset.
2. Separate predictors and the `Label` target.
3. Split data into training (168,588 records) and test (42,148 records) sets.
4. Apply the notebook's preprocessing pipeline.
5. Train Logistic Regression, Random Forest, and XGBoost.
6. Compare accuracy, macro precision, macro recall, and macro F1.
7. Review the XGBoost classification report, confusion matrix, and feature importance.
8. Document limitations and next steps.

> Reproducibility note: The exact preprocessing choices, model hyperparameters, random seeds, dataset version, and dataset citation should be taken from the original notebook and dataset source before claiming full reproducibility. Do not invent them.

## Tools

The analysis used Python-based machine-learning workflows. The exact package versions should be captured from the original environment before finalizing `requirements.txt`.

## Limitations and future work

- The results are from one prepared dataset and one held-out test split.
- Class representation varies, and XSS test support is relatively small.
- The current analysis is offline; it is not a deployed real-time IDS.
- Feature importance indicates model reliance, not causality.

Future work could test class weighting or resampling, add web-application-specific features, validate on independent datasets, tune hyperparameters, add explainability methods such as SHAP, and prototype a real-time inference pipeline.

## Data and responsible use

Do not commit private data, credentials, tokens, or datasets unless redistribution is permitted. This repository should contain code, documentation, and permitted derived figures—not a dataset copied from a source without checking its license and terms.

## Author contribution and evidence

This repository is intended to document the author's project workflow. To make the work independently reviewable, add:
- the original Colab notebook with relevant code and outputs;
- the generated figures;
- the final report;
- a short note explaining your own contribution and any libraries, datasets, tutorials, or collaborators used.

A name on a report or a GitHub commit history alone does not prove authorship. Keep the notebook and work artifacts consistent with the claims in this README.

## Citation

Add the exact dataset citation and access details from the original dataset source. Do not cite an assumed dataset version or invent publication metadata.
