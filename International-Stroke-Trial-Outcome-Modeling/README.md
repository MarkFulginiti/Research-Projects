## International Stroke Trial Machine-Learning Pipeline  
**Prediction of Six-Month Mortality, Dependency, and Recovery**

This project develops and evaluates a shared machine-learning framework for predicting three six-month outcomes after acute ischemic stroke using data from the International Stroke Trial.

**[View the complete analysis notebook](./IST_Six_Month_Outcome_Modeling_Pipeline_Final_20260726.ipynb)**

### Overview

The analysis compares six classification methods across six-month mortality, dependency, and recovery using a common predictor set and evaluation framework. Outcome-specific datasets are created by excluding only observations missing the selected outcome.

All preprocessing, including numeric standardization and categorical encoding, is performed within each modeling pipeline and refitted separately within every cross-validation training fold. This structure prevents validation and test information from entering model development.

### Methods

- Outcome-specific modeling of:
  - six-month mortality (`FDEAD`)
  - six-month dependency (`FDENNIS`)
  - six-month recovery (`FRECOVER`)
- Stratified 80/20 training-test split
- Five-fold stratified cross-validation
- Fold-specific numeric standardization and categorical encoding
- Grid-search hyperparameter tuning
- Six candidate model classes:
  - logistic regression
  - random forest
  - linear discriminant analysis
  - quadratic discriminant analysis
  - gradient boosting
  - neural network
- Balanced accuracy as the primary model-selection criterion:

$$\text{Balanced Accuracy}= \frac{\text{Sensitivity}+\text{Specificity}}{2}= \frac{1}{2}\left(\frac{TP}{TP+FN}+ \frac{TN}{TN+FP}\right)$$

- ROC-AUC as the secondary measure of discrimination
- Held-out evaluation using accuracy, balanced accuracy, ROC-AUC, precision, recall, and F1 score
- Calibration assessment using calibration curves and Brier scores
- Training-validation comparisons to assess overfitting
- Model interpretation using:
  - logistic-regression coefficients and odds ratios
  - gradient-boosting permutation importance

### Key Findings

Predictive performance differed more across outcomes than across model classes. Mortality was the most predictable outcome, dependency showed intermediate performance, and recovery was the most difficult to distinguish.

Within each outcome, several models produced similar cross-validation and held-out performance. No classifier dominated consistently across all three outcomes, and simpler methods such as logistic regression and linear discriminant analysis remained competitive with random forest, gradient boosting, and the neural network.

Random forest generally exhibited the largest training-validation performance gaps, indicating greater overfitting. Gradient boosting frequently achieved strong held-out performance with less evidence of overfitting. Age, level of consciousness, baseline neurological deficits, and stroke subtype repeatedly contributed predictive information across outcomes.

Dependency probabilities were comparatively well calibrated, whereas mortality and recovery probabilities were generally overestimated. These results demonstrate that model assessment should consider discrimination, calibration, stability, and classification tradeoffs rather than relying on a single performance metric.

### Purpose

This project demonstrates the construction of reusable, leakage-resistant machine-learning pipelines for clinical outcome prediction. It emphasizes reproducible model comparison, careful separation of model development from held-out evaluation, and interpretation of predictive performance across related outcomes.

The models are intended as exploratory prognostic tools. Reported coefficients and predictor importances describe predictive relationships rather than causal effects and should not be interpreted as evidence of treatment benefit or independent causal association.
