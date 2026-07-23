# Predicting Abalone Age from Physical Measurements

Comparing linear and non-linear models for estimating abalone age from external
physical measurements, with regression diagnostics and a written analysis of why
performance plateaus.
 
## Problem
 
An abalone's age is determined by cutting the shell, staining it, and counting
growth rings under a microscope — a slow and destructive process. If age could be
estimated from external measurements such as length, diameter, height, and weight,
it could be done non-destructively and at scale.
 
This project tests how far those measurements actually get you.
 
## Data
 
UCI Abalone dataset — <!-- TODO: number of observations --> observations, eight
physical measurements plus ring count. Age is ring count + 1.5 years.
 
## Approach
 
**Multiple linear regression (`Project.R`)** — Fit an OLS model of ring count on
the physical measurements. Applied a log transformation to the response to improve
normality and stabilize variance, and used Cook's Distance to identify and remove
influential observations. Evaluated with R², adjusted R², F-statistics, and
diagnostic plots.
 
**Random Forest (`RandomForest.ipynb`)** — Tested whether a non-linear ensemble
could capture relationships the linear model missed.
 
**Support Vector Machine (`SVM.ipynb`)** — Tested a second non-linear approach with
different inductive biases.
 
**K-Means clustering (`KMeansClustering.ipynb`)** — Exploratory. Ring count is a
discrete integer, which produces visible banding in the predictor–response plots.
This notebook examined whether unsupervised structure in the feature space
corresponded to those bands.
 
## Results
 
<!-- TODO: fill in actual figures -->
 
| Model | R² | RMSE |
|---|---|---|
| Multiple linear regression (log-transformed) | ~0.40 | |
| Random Forest | | |
| SVM | | |
 

## Key Findings
 
Non-linear models produced only marginal improvement over the linear baseline.
This points to a limit in the data rather than in the models: external physical
measurements capture part of what determines an abalone's ring count, but not
enough for added model complexity to help. Predicting age reliably would likely
require features this dataset does not contain — environmental conditions, water
temperature, or food availability.
 
A note on metrics: adjusted R² penalizes a model by its number of predictors,
which is well defined for OLS and not directly comparable for tree ensembles or
SVMs. Plain R² is used for cross-model comparison, alongside RMSE as an
interpretable error measure in rings.
 
## Repository contents
 
| File | Contents |
|---|---|
| `Project.R` | Linear regression, transformations, and diagnostics |
| `RandomForest.ipynb` | Random forest model |
| `SVM.ipynb` | Support vector machine model |
| `KMeansClustering.ipynb` | Exploratory clustering |
| `Final Report.pdf` | Full written analysis |
| `Abalone Poster.pdf` | Poster presented at UT's Fall Undergraduate Research Forum |
| `abalone.data` | UCI Abalone dataset |
 
## Next steps
 
- XGBoost, to complete the non-linear model comparison
- Reframe as ordinal classification over binned age ranges, which suits the
  discrete target and allows classification metrics
- Report RMSE and MAE across all models for a directly interpretable error measure
## Presented at
 
University of Tampa Fall Undergraduate Research Forum

<img width="1186" height="891" alt="Research poster: predicting abalone age from physical measurements" src="https://github.com/user-attachments/assets/e1ab8351-06e4-4bfd-8901-c3a7914adc6a" />
