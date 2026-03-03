# Modeling Your Data II

## Regression, Uncertainty, and Interpretation

---

## Overview

In *Modeling Your Data I*, we focused on distributions, variability, and the logic of modeling. We asked: *What does our outcome look like?*

Now we ask a more ambitious question:

> How do other variables explain variation in our outcome?

This module introduces **linear regression** as a framework for estimating relationships between variables while explicitly quantifying uncertainty.

Regression allows us to:

* Estimate the direction and magnitude of relationships
* Control for multiple predictors simultaneously
* Test hypotheses formally
* Generate predictions with confidence intervals

We move from description to **inference**.

---

!!! tip inline end "Learning Objectives"

* Understand the logic of linear regression
* Interpret coefficients substantively (not mechanically)
* Distinguish statistical significance from substantive significance
* Visualize fitted values and confidence intervals
* Recognize assumptions of linear regression

---

## TLDR;

Regression models estimate relationships between variables — but interpretation requires discipline.

### Common pitfalls to avoid

* Interpreting correlation as causation
* Ignoring model assumptions
* Focusing only on p-values
* Overlooking effect size magnitude
* Adding controls without theoretical justification

---

# From Means to Models

Previously, we estimated a single mean:

[
Y = \beta_0 + \epsilon
]

Now we extend this idea:

[
Y = \beta_0 + \beta_1 X + \epsilon
]

Where:

* ( Y ) = outcome variable
* ( X ) = predictor variable
* ( \beta_0 ) = intercept
* ( \beta_1 ) = slope (effect of X on Y)
* ( \epsilon ) = unexplained variation

This is the core of **ordinary least squares (OLS)** regression.

---

# Hack Time: A Simple Linear Regression

Let’s expand our previous example. Suppose `case_complexity` predicts `time_to_iep`.

```python
import pandas as pd
import statsmodels.api as sm
import numpy as np

# Create synthetic predictor
np.random.seed(42)
df["case_complexity"] = np.random.normal(5, 1.5, size=len(df))

# Define variables
X = sm.add_constant(df["case_complexity"])
y = df["time_to_iep"]

# Fit model
model = sm.OLS(y, X).fit()

print(model.summary())
```

---

## How to Read the Output

Focus on:

* **coef** → estimated effect size
* **std err** → uncertainty
* **t** → test statistic
* **P>|t|** → probability of observing this effect if the null were true
* **R-squared** → proportion of variance explained

But do not stop there.

Ask:

* Is the sign theoretically plausible?
* Is the magnitude substantively meaningful?
* Does the confidence interval include zero?

---

# Visualizing the Model

Visualization clarifies interpretation.

```python
import altair as alt

# Create predicted values
df["predicted"] = model.predict(X)

base = alt.Chart(df)

points = base.mark_circle(size=60).encode(
    x="case_complexity",
    y="time_to_iep"
)

line = base.mark_line(color="red").encode(
    x="case_complexity",
    y="predicted"
)

points + line
```

Interpretation:

* Each point = observed outcome
* Red line = model’s best linear estimate
* Vertical distance = residual

---

# Confidence Intervals Matter

Point estimates are incomplete without uncertainty.

```python
pred = model.get_prediction(X)
ci = pred.summary_frame(alpha=0.05)

df["ci_lower"] = ci["mean_ci_lower"]
df["ci_upper"] = ci["mean_ci_upper"]
```

Then visualize the interval band.

This teaches a critical lesson:

> Statistical modeling is about estimating plausible ranges — not just single numbers.

---

# Multiple Regression

Rarely is one predictor sufficient.

We extend the model:

[
Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \epsilon
]

This allows us to:

* Control for confounding variables
* Isolate conditional relationships
* Improve predictive performance

Example:

```python
df["student_age"] = np.random.normal(10, 2, size=len(df))

X_multi = sm.add_constant(df[["case_complexity", "student_age"]])
model_multi = sm.OLS(y, X_multi).fit()

print(model_multi.summary())
```

Interpret coefficients as:

> The expected change in Y for a one-unit increase in X₁, holding other variables constant.

The phrase “holding constant” is central to regression interpretation.

---

# Assumptions of OLS

Regression is powerful, but conditional on assumptions:

1. Linearity
2. Independence of errors
3. Homoscedasticity
4. Normally distributed residuals (for inference)
5. No perfect multicollinearity

Check residual plots:

```python
residuals = model.resid

alt.Chart(pd.DataFrame({"residuals": residuals})).mark_bar().encode(
    x=alt.X("residuals:Q", bin=True),
    y="count()"
)
```

Never assume assumptions are satisfied — inspect them.

---

# Substantive vs Statistical Significance

An effect can be statistically significant but trivial in magnitude.

Always ask:

* Does a 0.05 unit change matter in real-world terms?
* Would policymakers care about this magnitude?
* Is the confidence interval narrow enough to be meaningful?

Modeling is not about stars next to coefficients.

It is about interpretation grounded in theory.

---

# Hack Time

Continue working in **07_data-modeling-insights.ipynb**.

Focus on:

* Adding one predictor at a time
* Comparing R² values
* Interpreting coefficients in plain language
* Visualizing fitted relationships

Ask yourself after each model:

* What changed?
* Why did it change?
* Does this align with theoretical expectations?

---

# Additional Resources

* Statsmodels Documentation: [https://www.statsmodels.org/](https://www.statsmodels.org/)
* Regression Diagnostics Overview: [https://online.stat.psu.edu/stat501/](https://online.stat.psu.edu/stat501/)
* Visualization Best Practices: [https://datavizcatalogue.com/](https://datavizcatalogue.com/)
