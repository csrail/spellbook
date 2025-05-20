---
layout: spell
date: 2025-05-13
---

Shapiro-Wilk test tests for the normality of the data inputted.

This data can be the datapoints itself when assessing the normality of data from 2 sample data from two independent populations:

```r
# apply Shapiro-Wilk test onto a numeric vector of data values
# apply test to both data samples
shapiro.test(vector_first_sample)
shapiro.test(vector_second_sample)
```

$H_0 : \text{data is normal}$\
$H_A : \text{data is not normal}$\
$\Rightarrow \text{p-value < 0.05} \rightarrow \text{reject} H_0, \text{data is not normal}$

[$\Rightarrow$ Assessing normality of data when testing 2 sample data from independent populations](/spellbook/spells/data_analytics/testing_2_sample_data_from_independent_populations.html)

<br>

Or this data can be the residuals from a linear model object:

```r
# apply Shapiro-Wilks test onto a vector of residuals
shapiro.test(lm_object$residuals)
```

$H_0 : \text{residuals are normal}$\
$H_A : \text{residuals are not normal}$\
$\Rightarrow \text{p-value < 0.05} \rightarrow \text{reject} H_0,\ \text{residuals are not normal}$

[$\Rightarrow$ Using Residuals to assert the quality of the Regression Model](/spellbook/spells/data_analytics/regression_model_assumptions.html)
