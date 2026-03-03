# Modeling Your Data III

## Categorical Predictors and Interactions

---

## Overview

So far, we’ve focused on **numeric predictors** and linear regression. But much of political science data — like **gender, party affiliation, region, or policy type** — is **categorical**.

In this module, we will learn how to:

* Include categorical variables in regression models
* Interpret coefficients for categorical predictors
* Model interactions between variables
* Visualize conditional relationships

Categorical predictors allow models to answer nuanced questions:

> Does the effect of case complexity on `time_to_iep` differ for different student types?

---

!!! tip inline end "Learning Objectives"

* Encode categorical predictors appropriately
* Interpret dummy variable coefficients
* Test and interpret interaction effects
* Visualize conditional relationships
* Avoid common pitfalls with categorical modeling

---

## TLDR;

Treat categorical variables carefully: coding choices determine your interpretation.

### Common pitfalls to avoid

* Forgetting to encode categories as numeric/dummies
* Interpreting reference groups incorrectly
* Ignoring interaction terms when theory predicts conditional effects
* Overfitting by creating too many categories for small datasets

---

# Including Categorical Predictors

Suppose we add a **student_type** variable: `'regular'` vs `'special_education'`.

```python id="cat-model"
import pandas as pd
import numpy as np
import statsmodels.api as sm

# Add categorical variable
np.random.seed(42)
df["student_type"] = np.random.choice(["regular", "special_education"], size=len(df))

# Create dummy variables
df = pd.get_dummies(df, columns=["student_type"], drop_first=True)

# Define predictor and outcome
X_cat = sm.add_constant(df[["case_complexity", "student_type_special_education"]])
y = df["time_to_iep"]

# Fit model
model_cat = sm.OLS(y, X_cat).fit()
print(model_cat.summary())
```

**Interpretation tip:**

* Coefficient for `student_type_special_education` = difference in average `time_to_iep` compared to the reference group (`regular`) **holding other predictors constant**.

---

# Interactions Between Variables

Sometimes, the effect of one predictor depends on another. For example:

> Does the effect of `case_complexity` on `time_to_iep` differ by `student_type`?

```python id="interaction-model"
# Create interaction term
df["interaction"] = df["case_complexity"] * df["student_type_special_education"]

# Fit model with interaction
X_int = sm.add_constant(df[["case_complexity", "student_type_special_education", "interaction"]])
model_int = sm.OLS(y, X_int).fit()
print(model_int.summary())
```

**Interpretation:**

* `case_complexity` → effect for the reference group (`regular`)
* `interaction` → additional effect for `special_education` students
* Sum `case_complexity + interaction` to get slope for special education students

---

# Visualizing Interactions

Visualization helps interpret conditional relationships:

```python id="interaction-plot"
import altair as alt

# Predicted values
df["predicted_int"] = model_int.predict(X_int)

alt.Chart(df).mark_circle(size=60).encode(
    x="case_complexity",
    y="time_to_iep",
    color="student_type_special_education:N"
) + alt.Chart(df).mark_line(size=2).encode(
    x="case_complexity",
    y="predicted_int",
    color="student_type_special_education:N"
)
```

Key points:

* Each line = predicted relationship by student type
* Slope differences = interaction effect
* Observed points show data variability

---

# Hack Time

Continue in **07_data-modeling-insights.ipynb**:

1. Add a new categorical variable (`region`, `policy_type`, etc.)
2. Fit a model with and without interactions
3. Compare coefficients and predicted values
4. Visualize conditional slopes
5. Ask:

* How do coefficients change across groups?
* Are interactions meaningful substantively?
* How does visualization clarify interpretation?

---

# Assumptions & Pitfalls

* Ensure categories have enough observations; too few leads to unstable estimates
* Avoid multicollinearity when including many dummies
* Interpret interactions **in context**, not mechanically

---

# Additional Resources

* [Statsmodels Categorical Data](https://www.statsmodels.org/stable/examples/notebooks/generated/categorical.html)
* [Interpreting Interactions](https://stats.idre.ucla.edu/other/mult-pkg/faq/general/faq-what-is-an-interaction/)
* [Visualization of Interactions](https://datavizcatalogue.com/)
