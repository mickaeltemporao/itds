# 📘 Modeling Your Data – Quick Reference

---

## 1️⃣ Descriptive Modeling & Distributions (Modeling I)

**Goal:** Understand your outcome before modeling.

**Key Concepts:**

* Mean, median, SD, min/max
* Histograms, density plots
* Outliers and skewness

**Tips:**

* Visualize distributions first
* Check for implausible values
* Summary stats ≠ conclusions

**Pitfalls:**

* Ignoring variability
* Modeling before exploring

**Visual Reminder:**
Histogram + mean line

---

## 2️⃣ Linear Regression & Continuous Outcomes (Modeling II)

**Goal:** Estimate relationships between numeric predictors and a continuous outcome.

**Equation:**
[
Y = \beta_0 + \beta_1 X + \epsilon
]

**Key Concepts:**

* Coefficients → slope/impact
* R² → proportion of variance explained
* Residuals → model fit

**Tips:**

* Start simple: one predictor at a time
* Interpret coefficients in context, not mechanically
* Visualize predicted vs observed

**Pitfalls:**

* Correlation ≠ causation
* Ignoring model assumptions

**Visual Reminder:**
Scatterplot + fitted line + residuals

---

## 3️⃣ Categorical Predictors & Interactions (Modeling III)

**Goal:** Model differences across groups and conditional relationships.

**Equation:**
[
Y = \beta_0 + \beta_1 X_1 + \beta_2 D + \beta_3 (X_1*D) + \epsilon
]

**Key Concepts:**

* Dummy variables → encode categories
* Reference group matters
* Interaction terms → slope differs by group

**Tips:**

* Visualize predicted lines by category
* Sum main + interaction coefficients to interpret
* Ensure enough observations per category

**Pitfalls:**

* Misinterpreting reference group
* Too many categories → unstable estimates

**Visual Reminder:**
Line plot by group showing interactions

---

## 4️⃣ Logistic Regression & Binary Outcomes (Modeling IV)

**Goal:** Estimate probability of a binary event.

**Equation:**
[
\log\frac{P(Y=1)}{1-P(Y=1)} = \beta_0 + \beta_1 X_1 + \cdots
]

**Key Concepts:**

* Coefficients → log-odds
* Odds ratio = exp(coef)
* Predicted probabilities: 0 → 1

**Tips:**

* Transform coefficients to probabilities for interpretation
* Include interactions to test conditional effects
* Evaluate model fit: ROC, AUC, confusion matrix

**Pitfalls:**

* Treating binary outcome as continuous
* Misinterpreting odds ratios as probability changes
* Ignoring rare events

**Visual Reminder:**
Scatterplot of predictor vs predicted probability by group

---

## 🔑 General Modeling Tips

* Always explore data before modeling
* Check assumptions: linearity, homoscedasticity, independence
* Visualize predicted vs observed outcomes
* Focus on **substantive significance**, not just statistical significance
* Keep models interpretable: one predictor at a time before adding complexity

---

This page can be **printed or shared as a PDF** for quick reference during labs, Hack Time, or analysis.
