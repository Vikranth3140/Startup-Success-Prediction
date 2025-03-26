# Predicting Startup Trajectories with Dual-Task Machine Learning: Funding and Fate

[![Python 3.6+](https://img.shields.io/badge/python-3.6+-blue.svg)](https://www.python.org/downloads/release/python-360/)
[![sk-learn](https://img.shields.io/badge/scikit-learn-grey.svg?logo=scikit-learn)](https://scikit-learn.org/stable/whats_new.html)
![arXiv](https://img.shields.io/badge/arXiv-pending-red.svg)

This repository contains the code, data, and paper for a dual-task machine learning framework to predict startup success, focusing on venture capital funding (`has_VC`) and final status (`acquired` or `closed`). Leveraging a 923-sample Kaggle dataset, we explore key predictors like team networks and funding timelines, achieving top accuracies of 0.79 (KNN) for funding and 0.83 (Logistic Regression) for status.

## Overview

Startups face a high failure rate (>85% within five years), making predictive tools vital for entrepreneurs and investors. This project introduces a novel dual-task approach:
- **Task 1**: Predicts if a startup secures venture capital (`has_VC`) using a 120-sample subset.
- **Task 2**: Forecasts final status (`acquired` or `closed`) across the full dataset.

We employ Random Forest, KNN, SVM, and Logistic Regression, with preprocessing via imputation, encoding, scaling, and feature selection (`SelectKBest`). Results highlight team strength (`relationships`) and milestones as key drivers, though Random Forest’s perfect 1.0 status accuracy suggests potential overfitting.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Vikranth3140/Startup-Success-Prediction.git
   cd Startup-Success-Prediction
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
   *Requires Python 3.6+.*

## Key Findings

- **VC Funding (`has_VC`)**:
  - KNN: 0.79 accuracy, 0.86 F1-score (negatives).
  - Top features: `relationships`, `age_last_funding_year`.
- **Status**:
  - Logistic Regression: 0.83 accuracy, balanced F1-scores (0.86 acquired, 0.77 closed).
  - Random Forest: 1.0 accuracy (needs validation).
- Insight: Funding boosts resources, but team and milestones drive long-term success.

## Paper

The full study is detailed in our paper: [Predicting Startup Trajectories with Dual-Task Machine Learning: Funding and Fate.pdf](Paper.pdf).

## Dependencies

- `scikit-learn==1.2.2`
- `pandas==1.5.3`
- `numpy==1.24.2`
- `matplotlib==3.7.1` (for EDA plots)

See `requirements.txt` for the full list.

## Contributing

We welcome contributions! Please:
1. Fork the repo.
2. Create a branch (`git checkout -b feature-name`).
3. Commit changes (`git commit -m "Add feature"`).
4. Push (`git push origin feature-name`).
5. Open a Pull Request.

Focus areas:
- Cross-validation for Random Forest.
- Dynamic feature integration (e.g., time-series data).
- Hyperparameter tuning.

## License

This project is licensed under the [MIT License](LICENSE).

## Authors

- **Vikranth Udandarao** - [vikranth22570@iiitd.ac.in](mailto:vikranth22570@iiitd.ac.in)
- **Pratham Kamani** - [prathamk.ai22@bmsce.ac.in](mailto:prathamk.ai22@bmsce.ac.in)

## Citation

Pending arXiv publication. For now, cite as:
```
Udandarao, V., & Kamani, P. (2025). Predicting Startup Trajectories with Dual-Task Machine Learning: Funding and Fate.
```