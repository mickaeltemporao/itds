# Modeling Your Data IV

## Logistic Regression and Binary Outcomes

---

## Overview

So far, we’ve modeled **continuous outcomes** like `time_to_iep`. But many research questions involve **binary outcomes**, such as:

* Did a bill pass? (yes/no)
* Did a student meet a deadline? (yes/no)
* Is a respondent Democrat or Republican?

**Logistic regression** allows us to model binary outcomes, estimating the **probability** of an event occurring as a function of predictors.

Key differences from linear regression:

1. Outcome is **0 or 1**, not continuous
2. Coefficients estimate changes in the **log-odds**, not the raw outcome
3. Predicted values are probabilities between 0 and 1
4. Nonlinear relationship between predictors and outcome

---

!!! tip inline end "Learning Objectives"

* Understand the logic of logistic regression
* Interpret coefficients in terms of **odds ratios**
* Predict probabilities for binary outcomes
* Visualize predicted probabilities and confidence intervals
* Handle categorical predictors and interactions in binary models

---

## TLDR;

Linear regression assumptions fail for binary outcomes. Logistic regression is designed for probabilities but requires careful interpretation.

### Common pitfalls to avoid

* Treating binary outcomes as continuous
* Interpreting coefficients as direct probability changes
* Ignoring model fit and classification performance
* Overlooking rare events (imbalanced outcomes)

---

# Logistic Regression Formula

Logistic regression models the **log-odds**:

[
\log\frac{P(Y=1)}{1-P(Y=1)} = \beta_0 + \beta_1 X_1 + \cdots + \beta_k X_k
]

Where:

* ( P(Y=1) ) = probability the outcome occurs
* ( \beta ) coefficients estimate **change in log-odds** per unit change in predictor
* Can transform to **odds ratio**: ( OR = e^{\beta} )

---

# Hack Time: Logistic Regression in Python

Let’s create a binary outcome: `met_deadline` (1 = yes, 0 = no), predicted by `case_complexity` and `student_type`.

```python id="logit-model"
import statsmodels.api as sm

# Simulate binary outcome
np.random.seed(42)
df["met_deadline"] = np.random.binomial(1, p=0.7 - 0.05*(df["case_complexity"]-5), size=len(df))

# Define predictors
X_logit = sm.add_constant(df[["case_complexity", "student_type_special_education"]])
y_logit = df["met_deadline"]

# Fit logistic regression
logit_model = sm.Logit(y_logit, X_logit).fit()
print(logit_model.summary())
```

---

## Interpreting Coefficients

* **Coefficient ((\beta))** → change in log-odds for a one-unit increase in predictor
* **Exponentiated ((e^{\beta}))** → **odds ratio**: multiplicative change in odds

```python id="odds-ratio"
odds_ratios = np.exp(logit_model.params)
print(odds_ratios)
```

Example interpretation:

* Odds ratio > 1 → predictor increases odds of success
* Odds ratio < 1 → predictor decreases odds of success

---

# Predicted Probabilities

We can compute **predicted probabilities** for interpretation and visualization:

```python id="pred-prob"
df["pred_prob"] = logit_model.predict(X_logit)

alt.Chart(df).mark_circle(size=60).encode(
    x="case_complexity",
    y="pred_prob",
    color="student_type_special_education:N"
)
```

* Y-axis = probability of meeting the deadline
* Differences in slopes or levels = effect of `student_type`

---

# Interactions in Logistic Regression

Interactions are also possible:

```python id="logit-interaction"
df["interaction"] = df["case_complexity"] * df["student_type_special_education"]

X_logit_int = sm.add_constant(df[["case_complexity", "student_type_special_education", "interaction"]])
logit_model_int = sm.Logit(y_logit, X_logit_int).fit()
print(logit_model_int.summary())
```

Interpretation:

* `case_complexity` → effect for reference group
* `interaction` → additional effect for special education students
* Transform to probabilities to make interpretation intuitive

---

# Model Fit & Diagnostics

Check classification performance:

* Confusion matrix
* Accuracy, precision, recall
* ROC curve and AUC

```python id="roc-curve"
from sklearn.metrics import roc_curve, roc_auc_score

y_pred_prob = logit_model.predict(X_logit)
fpr, tpr, thresholds = roc_curve(y_logit, y_pred_prob)
auc = roc_auc_score(y_logit, y_pred_prob)
print(f"AUC: {auc:.2f}")
```

> Logistic regression is about **predicting probabilities and assessing fit**, not just significance.

---

# Hack Time

In **07_data-modeling-insights.ipynb**:

1. Add a new binary outcome (e.g., `policy_passed`)
2. Fit logistic regression with numeric and categorical predictors
3. Include interaction terms and visualize predicted probabilities
4. Compare odds ratios to interpret effects
5. Ask:

* Which predictors increase or decrease probability?
* Are interaction effects meaningful?
* Does the model provide a good fit to data?

---

# Additional Resources

* Statsmodels Logistic Regression: [https://www.statsmodels.org/stable/logit.html](https://www.statsmodels.org/stable/logit.html)
* UCLA Logistic Regression Tutorial: [https://stats.idre.ucla.edu/stata/faq/what-is-logistic-regression/](https://stats.idre.ucla.edu/stata/faq/what-is-logistic-regression/)
* Odds Ratios vs Probabilities Visualization: [https://datavizcatalogue.com/](https://datavizcatalogue.com/)

