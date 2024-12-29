---
layout: spell
date: 16-12-2024
---

let $N(x)$ be a polynomial\\
let $D(x)$ be a polynomial\\
A rational function takes the form $$\begin{align}f(x) = \frac{N(x)}{D(x)}\end{align}$$

let $x \in \mathbb{R}$\\
Domain: $$\{ x | D(x) \ne 0 \}$$ or $(-\infty, 0) \cup (0, \infty)$\\
$x$ can be any real number such that $D(x)$ does not equal 0.

**Asymptotes** are a visualisation of the approach towards infinity.

<br>

The **vertical asymptote** $x = a$ exists for the graph of $f$ when the returning value of $f(x)$ approaches infinity or negative infinity, as $x$ approaches $a$.\\
The **vertical asymptote** $x = a$ exists for the graph of $f$ when $f(x) \to \infty$ or $f(x) \to -\infty$ as $x \to a$, either from the left or the right.\\
When $[(x \to_{from the left} a) \land (f(x) \to \infty)] \rightarrow \text{graph moves up}$\\
When $[(x \to_{from the right} a) \land (f(x) \to \infty)] \rightarrow \text{graph moves up}$ 

When $[(x \to_{from the left} a) \land (f(x) \to -\infty)] \rightarrow \text{graph moves down}$  
When $[(x \to_{from the right} a) \land (f(x) \to -\infty)] \rightarrow \text{graph moves down}$  
<br>

<u>Testing for Vertical Asymptotes:</u>

Let $$\begin{align}f(x) = \frac{N(x)}{D(x)}\end{align}$$ be a rational function.

The zeroes of the denominator that are not the zeroes of the numerator.
- The shared zero between the denominator and the numerator form a hole in the graph.
- The remaining zeroes of the denominator will be vertical asymptotes

<br>

The **horizontal asymptote** $y = b$ exists for the graph of $f$ when the returning value of $f(x)$ approches the horizontal line $b$ as $x$ approaches infinity or negative infinity.\\
The **horizontal asymptote** $y = b$ exists for the graph of $f$ when the returning value of $f(x) \to b$ as $x \to \infty$  or $x \to -\infty$.\\
When $b$ is positive, then graph always moves up and plateaus when $x$ is approaching from the left or right.\\
When $b$ is negative, then graph always moves down and plateaus when $x$ is approaching from the left or right.
<br>

<u>Testing for Horizontal Asymptotes:</u>

Let $$\begin{align}f(x) = \frac{N(x)}{D(x)}\end{align}$$ be a rational function.

- $\text{degree}(N(x) < D(x)) \rightarrow \text{horizontal asymptote} : y=0$
- $\text{degree}(N(x) = D(x)) \rightarrow \text{horizontal asymptote} : \text{ratio of leading coefficients}$
- $\text{degree}(N(x) > D(x)) \rightarrow \text{horizontal asymptote} : \text{does not exist}$

Colloquially:
- $\text{degree}(N(x) < D(x)) \rightarrow \text{the denominator overwhelms the numerator}$
- $\text{degree}(N(x) > D(x)) \rightarrow \text{the numerator overwhelms the denominator}$

