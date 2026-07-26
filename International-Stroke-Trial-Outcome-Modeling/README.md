
## International Stroke Trial Machine-Learning Pipeline  
**Prediction of Six-Month Mortality, Dependency, and Recovery**

This project compares six machine-learning methods for predicting mortality, dependency, and recovery six months after acute ischemic stroke.

### Overview

A shared, leakage-resistant pipeline was applied separately to each outcome. Preprocessing and hyperparameter tuning were performed within cross-validation before final evaluation on an untouched test set.

### Methods

- Logistic regression, random forest, LDA, QDA, gradient boosting, and neural network
- Stratified 80/20 training-test split
- Five-fold cross-validation and grid-search tuning
- Balanced accuracy as the primary selection criterion:

$$
\text{Balanced Accuracy}
=
\frac{\text{Sensitivity}+\text{Specificity}}{2}
$$

- Held-out discrimination, classification, calibration, and overfitting assessment
- Logistic-regression odds ratios and permutation importance

### Key Findings

Performance differed more across outcomes than across model classes. Mortality was most predictable, dependency was intermediate, and recovery was most difficult. No classifier dominated consistently, and simpler models remained competitive with more flexible methods. Age, consciousness, neurological deficits, and stroke subtype repeatedly contributed predictive information.

### Purpose

This project demonstrates reproducible clinical prediction using leakage-resistant pipelines, cross-validation, held-out evaluation, calibration assessment, and model interpretation. Results describe predictive relationships rather than causal effects and are not intended for clinical use.
