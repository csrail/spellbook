---
layout: spell
date: 2025-05-13
---

A set of design constraints must be met on the dataset in order to test on 2 samples of data from two independent populations.

Furthermore, if a parametric test is chosen, diagnostics must be applied onto the dataset to determine which specific two sample t-test to use.

## Design Constraints

- Ensure each population is randomly sampled.
- Ensure each population is independent.
- For each sample, check that sample size $n > 30$, then can rely on CLT for symmetry and Normal distribution of sample mean.
- If $n > 30$ perform a parametric test: use diagnostics to determine the specific two sample t-test to use.
- If $n < 30$ and distribution not normal, perform a non-parametric test

## Diagnostics for Parametric Test.

For each sample, check for normality and variance of the data.

Normality Check:

- Histogram
- QQ plot
- Shapiro-Wilk Normality test

Variance Check:

- F-test OR Levene's test

<br>

Data Normal $\rightarrow$ yes $\rightarrow$ F-test, variances the same? $\rightarrow$ yes $\Rightarrow$ 2 sample t-test with pooled variances\
Data Normal $\rightarrow$ yes $\rightarrow$ F-test, variances the same? $\rightarrow$ no $\Rightarrow$ 2 sample t-test with unequal variance\
Data Normal $\rightarrow$ no $\rightarrow$ Levene's test, variances the same? $\rightarrow$ yes $\Rightarrow$ 2 sample t-test with pooled variances\
Data Normal $\rightarrow$ no $\rightarrow$ Levene's test, variances the same? $\rightarrow$ no $\Rightarrow$ 2 sample t-test with unequal variance

## Non-Parametric Test

- Use the Wilcoxon Rank Sum Test.
