---
layout: spell
date: 2025-05-17
---

## Fitting a Linear Regression Model

In the context of a linear regression model, data is collected for the purpose of answering the question of whether a set of predictors (numeric or categorical) predicts for a continuous response variable.

When fitting a model to the data, there are three main values for the response variable $y$:

- $y_i$, the actual value of $y$ for the $i$th observation
- $\bar{y}$, the mean value of $y$ in relation to the null model
- $\hat{y}_i$, the predicted value of $y$ in relation to the linear model for the $i$th observation\
  $~~$

Following a fit, a relationship of variation is observed:

$\displaystyle\stackrel{\text{DATA}}{y_i - \bar{y}}\ =\ \stackrel{\text{FIT}}{(\hat{y}_i - \bar{y})}\ + \stackrel{\text{RESIDUALS}}{(y_i - \hat{y}_i)}$\
$~~$

Following a fit, the degrees of freedom available are also observable:

$\displaystyle\stackrel{\text{DATA}}{n}\ =\ \stackrel{\text{FIT}}{p}\ + \stackrel{\text{RESIDUALS}}{n - p}$

<br>

Quantification of the variation involves a squaring of the differences so that additive inverses are made to accumulate rather than negate.

$\displaystyle\text{Sum of Squares Model} = \text{SSM} = \sum_{i = 1}^{n} \hat{y}_i - \bar{y}$

$\displaystyle\text{Sum of Squares Error} = \text{SSE} = \sum_{i = 1}^{n} y_i - \hat{y}_i$

$\displaystyle\text{Sum of Squares Total} = \text{SST} = \text{SSM} + \text{SSE}$

<br>
<br>

### Residual Degrees of Freedom

$\displaystyle n = \text{number of independent observations}$\
$\displaystyle p = \text{number of coefficients estimated in the model}$\
$\displaystyle \Rightarrow \text{Residual Degrees of Freedom} = n-p $

### Residual Standard Error

$\displaystyle \text{Residual Standard Error} = \sqrt{\frac{\text{SS}_{\text{Error}}}{\text{Residual DF}}}$

<br>
<br>

### R-squared

The proportion of total variation in the response variable that is explained by the model using the explanatory variables.\
$\displaystyle R^2 = \frac{\text{SSM}}{\text{SST}}$

Useful when comparing models with the same number of predictors.

### Adjusted R-squared

The proportion of total variation in the response variable that is explained by the model using the explanatory variables after adjusting for residual degrees of freedom.\
$\displaystyle \text{Adjusted}\ R^2 = 1 - \left[(1 - R^2)\left(\frac{n-1}{n-p}\right)\right]$

Useful when comparing models with different number of predictors since R-squared will always improve when more predictors are added. Adjusted R-squared will take into the added complexity and penalise the inclusion of extra predictors when they do not add a meaningful contribution to predictive quality.
