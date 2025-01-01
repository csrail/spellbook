---
layout: spell
date: 31-12-2024
---

Let $f$ be a logarithmic function defined as $y = \log_a x \Leftrightarrow x = a^{y}$,\\
where base $a > 0, a \ne 1$, where $x > 0$

Thus when $\log_a$ is applied to $x$, it returns the exponent $y$ required to raise the base $a$ to the result $x$.\\
Logarithms are exponents.

Colloquially: What is the exponent that when applied to the base $a$ that returns $x$?

<br>

The logarithmic function with base $a$ is defined as $f(x) = \log_a x$

$D : (0, \infty) \Leftrightarrow D : \mathbb{R} > 0$, positive real numbers\\
$R : (-\infty, \infty) \Leftrightarrow R : \mathbb{R}$, all real numbers

$f(x)$ increases $\rightarrow a > 1$, increasing logarithmic, logarithmic growth\\
$f(x)$ decreases $\rightarrow 0 < a < 1$, decaying logarithmic, logarithmic decay

There is always an $x$ intercept at $(1,0)$\\
There is always a vertical asymptote at $x = 0 \Leftrightarrow$ y-axis.\\
The logarithmic function is one-to-one and hence has an inverse, the exponential function.\\
The curve is smooth and continuous.

<br>

Logarithms to base 10 are common logarithms.\\
Logarithms to base ${\rm e}$ are natural logarithms.\\
$\ y = \log_e x \Leftrightarrow x = {\rm e}^y$\\
$\ y = \ln x$ 

<br>

<u>Logarithmic properties:</u>
- $\log_a 1 = 0 \leftrightarrow a^{0} = 1$\\
$\log$ of one is zero to any base, because $a$ to the zero is one. 
<br>
<br>
- $\log_a a = 1 \leftrightarrow a^{1} = a$\\
$\log$ of a to base $a$ is one, because $a$ to the first power is $a$.
<br>
<br>
<br>
- $\log_a a^{x} = x$\\
$\log$ base $a$ of $a$ to the $x$ compactifies to $x$.
<br>
<br>
- $a^{\log_a x} = x$\\
$a$ to the power $\log$ base $x$ equals $x$.
<br>
<br>
<br>
- $\log_a x = \log_a y \Rightarrow x = y$\\
If $\log$ of $x$ equals $\log$ of $y$, then $x$ must equal $y$.
<br>
<br>
<br>
- $\begin{aligned}\log_a x = \frac{\log_{10} x}{\log_{10} a} = \frac{\ln x}{\ln a}\end{aligned}$\\
The $\log$ to base $a$ of $x$ is the quotient of $\log$ base ten of $x$ divided by the $\log$ base ten of $a$.\\
The $\log$ of $x$ to base $a$ is equal to the natural $\log$ of $x$ divided by the natural $\log$ of $a$.
<br>
<br>
<br>
- $\log_a (uv) = \log_a u + \log_b v$\\
The $\log$ to base $a$ of the product $u$ times $v$ equals the sum of two logarithms $\log$ base $a$ of $u$ plus $\log$ base $a$ of $v$.\\
The $\log$ of a product is the sum of their logarithms.
<br>
<br>
- $\begin{aligned}\log_a \left(\frac{u}{v}\right) = \log_a u - \log_b v\end{aligned}$\\
The log of a quotient is the difference of their logarithms.
<br>
<br>
<br>
- $\log_a u^{n} = n \log_a u$\\
The $\log$ of $u$ to a power $n$ is equal to $n$ $\log$ $u$

<br>

---

<br>

Logarithmic Differentiation:\\
Derivatives of sums is easy.  Derivatives of products are difficult.  Therefore having logarithms which break an expression from a product into sums aids with taking the derivative of an expression.