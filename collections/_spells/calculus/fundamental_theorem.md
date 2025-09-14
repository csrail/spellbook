---
layout: spell
date: 11-11-2024
---

This exposition outlines the fundamental theorem of calculus, comparing the following relationships:
- infinite processes vs taking a limit
- derivative vs antiderivative
- gradients vs estimates
- instantaneous rate of change vs integral (accretion of estimates)

<br>

---

<br>

Suppose you have a function $f(x)$.\\
For a given $x$ input value, a corresponding $f(x)$ output value is returned to create an ordered pair $(x, f(x))$.\\
From a single ordered pair, as a snapshot, it is not possible to determine the rate --- direction and magnitude --- at which the value $f(x)$ changes as $x$ changes.\\
But we know for every ordered pair $(x, f(x))$, this ordered pair relates to two other immediate ordered pairs such that $x \pm \Delta x$.

$\Rightarrow (x-\Delta x, f(x-\Delta x)) \rightarrow (x,f(x)) \rightarrow (x+\Delta x, f(x+\Delta x))$

Thus if we take the gradient between two ordered pairs $(x_0, f(x_0)) \wedge (x_1, f(x_1))$, we can approximate the gradient for a target $x_0$ value.  The closer the $x_1$ value used, the better the approximation of the gradient.  We can apply this process of taking a closer $x_1$ value to the target $x_0$ value an <u>infinite number of times</u> to calculate a better approximation.  This approach leads us to <u>taking the limit</u>, of which $x_1$ approaches 0 but never reaches it, expressed as $\lim_{\Delta x\to 0}$.

Thus the <u>instantaneous rate of change</u> of a function $f(x)$ for a given $x$ value is:

$\begin{aligned}
\lim_{\Delta x\to 0} \frac{f(x + \Delta x) - f(x)}{x + \Delta x - x}
\end{aligned}$

$\begin{aligned}
\Rightarrow \lim_{\Delta x\to 0} \frac{f(x + \Delta x) - f(x)}{x}
\end{aligned}$

<br>

When this infinite process of finding the instantaneous rate of change is applied to every possible value of $x$, we can determine a function $f^{\prime}(x)$ called the **derivative**.  Thus when the derivative is applied to any $x$ input value, the corresponding instantaneous rate of change $f^{\prime}(x)$ is returned. 

$\begin{aligned}
\frac{d}{dx}(f(x)) = \lim_{\Delta x\to 0} \frac{f(x + \Delta x) - f(x)}{x}
\end{aligned}$

<br>

---

<br>

Suppose you have a function $F(x)$.\\
A derivative of $F(x)$ is $F^{\prime}(x)$ which can be expressed as $f(x)$.\\
If we multiplied $f(x)$ with some $x$ value, the output would be some value in the dimension of $F(x)$.\\
If we multiplied $f(x)$ with some $x$, then this becomes an ordered pair $(x, f(x))$ for a given $x$ interval.\\
When a corresponding $f(x)$ is multiplied by its $x$ interval, the value returned is an estimate of the actual $F(x)$ value within that interval such that:

$\begin{aligned}
\overline{F(x + \Delta x)} = f(x + \Delta x) \cdot \Delta x
\end{aligned}$ 

This estimated value is either an underestimate or an overestimate depending on the $f(x)$ value used and the size of the $x$ interval.\\
As the $x$ interval becomes smaller, the estimate becomes more accurate.

The process of taking a smaller $x$ interval can be applied an infinite number of times to get a better estimate.  By taking a limit during this process, the estimate approaches the actual value in the very narrow interval.

It is the accretion of these estimates from successive narrow intervals that forms the integral:

$\begin{aligned}
(f(x_0) \cdot \Delta x) + (f(x_0 + \Delta x) \cdot \Delta x) + (f(x_0 + 2 \Delta x) \cdot \Delta x) + \ldots + (f(x_1) \cdot \Delta x)
\end{aligned}$ 

The integral can be expressed as the summation of successive estimates spanning between two $x$ values $x_0$ and $x_1$:

$\begin{aligned}
\int_{x_0}^{x_1} f(x)\, dx
\end{aligned}$

There can also be multiple parts to the span:

$\begin{aligned}
\int_{x_0}^{x_2} f(x)\, dx = \int_{x_0}^{x_1} f(x)\, dx + \int_{x_1}^{x_2} f(x)\, dx
\end{aligned}$

<br>

Suppose the following integral where $a = 0$ and $b > 0$:

$\begin{aligned}
\int_{a}^{b} f(x)\, dx
\end{aligned}$

Computing this integral requires the difference of the following two integrals $\int_{0}^{a}$ and $\int_{0}^{b}$ such that:

$\begin{aligned}
\Rightarrow \int_{0}^{b} f(x)\, dx - \int_{0}^{a} f(x)\, dx
\end{aligned}$

$\begin{aligned}
\Rightarrow F(b) - F(a)
\end{aligned}$

The surprising finding here is that the original function $F(x)$ we started with can help us compute these estimates in totality.\\
$F(x)$ is an **antiderivative** of $f(x)$, c.f. $f(x)$ is equivalent to $F^{\prime}(x)$ which is the derivative of $F(x)$.
