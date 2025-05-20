---
layout: spell
date: 2025-05-14
---

Assumptions in this explanation:

- for a given sample of data, we are describing how one explanatory variable relates to one response variable
- both variables are quantitative
- when the datapoints are visualised on a scatterplot, there is strong, positive, linear association between the two variables
- a linear model is applied onto the datapoints and a regression line is drawn onto the scatterplot

The linear model is a function which calculates the expected mean $y$ value of the response variable based on a fixed $x$ value of the explanatory variable. For every $x$ input given, a specific $y$ value is returned which is the average response value for a given explantory value.

To draw the regression line, take a seqeuence of $x$ values, starting from a minimum and ending at a maximum, with an infinite number of slices and compute each corresponding $\hat{y}$ value. Then plot each computed $(x,\hat{y})$ value onto the scatterplot and connect the dots.

For a given set of datapoints indexed with $i$ we can denote a specific datapoint with the ordered pair $(x_i, y_i)$. When the linear model is applied to input $x_i$, the predicted value returned is $\hat{y}_i$.

From a given datapoint, the $x_i$ value will be associated with the actual $y_i$ value of the datapoint. The $x_i$ value will also be associated with a linear model's $\hat{y}_i$ value. The difference between the linear model's $\hat{y}_i$ and the datapoint's $y_i$ is the residual $\epsilon_i$.

Formally stated, the linear model predicts an expected response:

$\hat{y}_i = \beta_0 + \beta_1 \cdot x_i$\
$\displaystyle \Leftrightarrow \text{Expected Response} = \beta_0 + \beta_1 \cdot \text{Predictor}$

Formally stated, the observed response in relation to the fitted linear model produces a residual:

$y_i = \beta_0 + \beta_1 \cdot x_i + \epsilon_i$\
$\displaystyle \Leftrightarrow \text{Observed Response} = \beta_0 + \beta_1 \cdot \text{Predictor} + \text{Error}$

<br>

The residual $\epsilon$ generated as a difference between the model's predicted response and the collected observed response is itself a random variable! As a random variable, the residuals have useful properties that can be investigated: further statistics and visualisations can be applied onto the residuals in order to assert the quality of the linear regression model.

[$\Rightarrow$ Visualisation: using Residuals to assert the quality of the Regression Model](/spellbook/spells/data_analytics/regression_model_assumptions.html)\
[$\Rightarrow$ Statistics: using Residuals to make inferences from the Regression Model ](/spellbook/spells/data_analytics/regression_model_inference.html)
