## Fuzzy Regression Discontinuity Design  
**Simulation-Based Examination of Estimator Performance**

This paper presents a simulation-based evaluation of fuzzy regression discontinuity (RD) estimators, with emphasis on finite-sample behavior, weak compliance, and local instrumental-variable identification.

### Overview
The study investigates how fuzzy RD estimators perform when treatment take-up changes only probabilistically at the cutoff. Using a controlled data-generating process, the analysis isolates the effects of first-stage strength, outcome curvature, smooth confounding, and treatment-effect heterogeneity on estimator bias, variance, and inference.

### Methods
- Smooth running variable with a known cutoff
- Probabilistic treatment assignment inducing a discontinuity in treatment probability

#### Estimators Considered
- naïve global regression
- incorrectly specified sharp RD
- fuzzy Wald estimator 
- local two-stage least squares (local 2SLS)
- bias-corrected fuzzy RD using rdrobust

#### Monte Carlo simulation study varying:
- first-stage strength (strong vs. weak compliance)
- curvature of the outcome surface
- smooth confounding correlated with the running variable
- treatment-effect heterogeneity

#### Robust summaries (median, interquartile range, trimmed means) and diagnostic plots to characterize instability under weak identification

### Key Findings
When compliance is sufficiently strong, design-aligned fuzzy RD estimators recover the local complier average treatment effect with small bias. Under weak compliance, local 2SLS exhibits extreme variance inflation driven by near-zero first-stage discontinuities, with a small number of replications dominating mean-based performance metrics such as RMSE. Robust summaries show that the typical estimator remains close to the target effect, indicating that instability arises primarily from tail behavior rather than large systematic bias. Bias-corrected inference via rdrobust delivers stable coverage across all scenarios.

### Purpose
This project clarifies the practical limits of fuzzy regression discontinuity designs and highlights the central role of first-stage strength in finite samples. The results emphasize the importance of robust inference, diagnostic checks, and careful interpretation when applying fuzzy RD methods in empirical work.



