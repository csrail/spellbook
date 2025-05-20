---
layout: spell
date: 2025-05-16
---

The quality of the linear regression model can be assessed by applying tests and visualisations onto the residuals of a linear model object.

Suppose the linear model object:

```r
# apply a linear model to the dataset
lm_object <- lm(response ~ explanatory, data="sample_data.df")
```

The **residuals** of the linear model need to satisfy a set of assumptions in order for the linear model to make meaningful inferences such as confidence intervals and prediction intervals.

## Normality

Assess whether the residuals follow a normal distribution.

### QQ Plots

- For a given Normal QQ Plot:
  - 50% of the data will be below the 0, and 50% of the data above the 0
  - 5th perncentile will be at -1.64, and the 95th percentile will be at 1.64
- residuals in the QQ plot stay within the 95% confidence interval and lie close to the straight diagonal line
- the residuals are randomly distributed about the diagonal line and do not follow an obvious sequence or pattern (e.g. curved line)
- at the outer extremity of the quantiles, a couple of residuals can exist outside the bands and this is expected behaviour

```r
# get basic QQ plot
plot(lm_object, which=2)
```

```r
# enhanced QQ plot with confidence interval banding
library(car)
qqPlot(lm_object$residuals)
```

## Shapiro-Wilks Test

[$\Rightarrow$ Shapiro Wilk Test](/spellbook/spells/data_analytics/shapiro_wilk_test.html)

```r
# apply Shapiro-Wilks test onto residuals
shapiro.test(lm_object$residuals)
```

## Variance

Assess whether the residuals have a constant variance (homoscedasticity).

- the residuals should show constant scatter
- the residuals should not follow a non-linear trend or pattern
- the residuals should not cluster
- ideally the red line should be horizontal and not bend; if the red line is bent then it is being pulled and influenced by the data points to become a curved line

```r
# get Residuals vs Fitted plot
plot(lm_object, which=1)
```

```r
# get sqrt(abs(Standardised Residuals)) vs Fitted Plot
# Standardisation refers to dividing Residuals by their Standard Deviation
# -> transforms the residual into a test statistic to observe how far it is away
# from the mean
# The Square Root draws in extreme values closer to the more common value
plot(lm_object, which=3)
```

## Outliers

Assess whether there are outliers in the residuals.

- Outliers can all be observed in the previous plots. For the Fitted vs Residuals, the outlier will be in the unit of the response variable. For the Scale-Location Plot, the outlier will be a positive standardised value that has been square rooted $\rightarrow$ if standardised, 95% of the output should be within -2 to 2 $\rightarrow$ then the absolute value taken so 95% of the output should be withint 0 to 2 $\rightarrow$ then after square rooting, the large values are anything greater than 1.414

```r
# get Standardised Residuals vs Leverage plot with Cook's Distance overlay
plot(lm_object, which=5)
```

## Appendix

```r
# Will plot all four plots listed above in a 2 by 2 grid
par(mfrow = c(2, 2))
plot(lm_object)
```
