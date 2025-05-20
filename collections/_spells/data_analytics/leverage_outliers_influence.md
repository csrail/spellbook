---
layout: spell
date: 2025-05-15
---

Leverage: an $x$ input / explanatory variable / predictor that is extreme has high leverage.

Outlier: a $y$ output / response variable / prediction that is extreme is an outlier.

Influence: a datapoint that has high leverage and is an outlier has the ability to influence the coefficients of the model. The datapoint has high influence when its inclusion or exclusion from the dataset changes the model's coefficients and hence the model.

## Testing Leverage

- Hat Matrix

## Testing Outliers

- Fitted vs Residuals Plot
  - outliers automatically labelled with their id
- sqrt(abs(Standardised Residuals)) vs Fitted Plot $\rightarrow$ Scale-Location Plot
  - outliers are at a y-value beyond 1.414
- QQ Plot
  - outliers are at a y value greater than 2 or a y value less than -2
- Residuals vs Leverage Plot $\rightarrow$ Cook's Distance
  - outliers are at a y value greater than 2 or a y value less than -2

## Testing Influence

- DFFITS $\rightarrow$ Difference in FIT Statistics
  - high influence observations have a high DFFITS
  - at the point of interest, take the difference of the vertical height between two lines of fit: the fitted line including the observation, and the fitted line excluding the observation
- Studentised Residual...
- Cook's Distance
  - high influence observations have a high Cook's distance
  - take the difference between the least squares estimates of the regression coefficients including the observation, and the least squares estimates of the regression coefficients excluding the observation
