# Abalone Age Prediction
### Can we predict the age of an abalone from its physical 
### measurements without cutting it open?

**Author:** Beakale Amenu Tefera  
**Institution:** University of Messina — First Year Data Science  
**Dataset:** UCI Abalone Dataset — 4177 observations  
**Language:** R — R Markdown  

---

## Research Question

Traditionally, determining the age of an abalone requires 
cutting the shell and counting rings under a microscope — 
a destructive and time consuming process. This project 
investigates whether physical measurements alone can 
predict abalone age accurately.

---

## Project Structure

**Section 1 — Data Preparation**
- Loaded UCI Abalone dataset
- Renamed columns for clarity
- Converted Sex to factor
- Derived Age from Rings + 1.5

**Section 2 — Exploratory Data Analysis**
- Age histogram — right skewed, peak at 10
- Age by Sex boxplot — Male highest median
- Pairwise plot — multicollinearity confirmed

**Section 3 — Descriptive Statistics**
- Age has largest SD (3.22) — prediction is challenging
- Height has highest positive skew (3.13)
- Length and Diameter show negative skew

**Section 4 — Statistical Testing**
- Kruskal-Wallis test confirmed Sex significantly 
  affects Age (p < 0.001)

**Section 5 — Correlation Analysis**
- Shell Weight strongest predictor (r = 0.63)
- All variables show at least moderate correlation
- Multicollinearity confirmed among predictors

**Section 6 — Linear Regression**
- Simple Linear Regression — R² = 0.39
- Multiple Linear Regression — Adjusted R² = 0.54
- Diagnostic plots confirmed non-linearity and 
  heteroscedasticity

**Section 7 — Classification**
- Age grouped into Young, Middle, Old
- Random Forest — 73.69% accuracy
- Shell Weight most important feature
- Old abalones — highest error (51.88%)

**Section 8 — Cross Validation**
- 10-Fold Cross Validation — 73.52% accuracy
- Difference of 0.17% confirms no overfitting
- Kappa score 0.524 — moderate agreement

**Section 9 — SMOTE**
- Class imbalance addressed using SMOTE
- Dataset balanced from 4177 to 7775 observations
- Accuracy improved from 73.69% to 85.95%
- Old abalone error dropped from 51.88% to 8.40%

---

## Key Findings

- Shell Weight is the strongest predictor of Age
- Physical measurements alone can classify age groups 
  with 85.95% accuracy after balancing
- Class imbalance was the primary limitation — 
  SMOTE resolved it effectively
- The relationship between measurements and Age 
  is non-linear — linear models have a ceiling at 54%

---

## Limitations

- Multicollinearity among physical measurements
- Non-linear growth relationship limits regression
- SMOTE generates synthetic — not real — observations
- Middle abalone error increased after SMOTE

---

## Packages Used

- ggplot2 — visualisation
- dplyr — data manipulation
- caret — cross validation
- corrplot — correlation heatmap
- reshape2 — data reshaping
- smotefamily — SMOTE resampling
- randomForest — classification
- gridExtra — plot layouts
- GGally — pairwise plots
- psych — descriptive statistics

---

## How To Run

1. Clone the repository
2. Open `Abalone RMarkdown.Rmd` in RStudio
3. Install required packages
4. Click `Knit` to generate the full report

---
