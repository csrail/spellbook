---
layout: spell
date: 15-12-2024
---

let $n$ be a non-negative integers.\\
let $a_{n},a_{n-1},\ldots,a_{2},a_{1},a_{0}$ be real numbers.\\
let $a_{n} \ne 0 \Rightarrow$  ensures that a highest degree exists.

A polynomial function in $x$ of degree $n$, with $a_{n}$ as the leading coeffiecient:

$f(x) = a_{n}x^{n} + a_{x_1}x^{n-1} + \ldots + a_{2}x^{2} + a_{1}x + a_{0}$

---
<br>

$$\begin{align}
  \begin{array}{1}
  \text{Polynomial of degree 1}& \Leftrightarrow & \text{Linear polynomial}\\
  f(x) = a_{1}x + a_{0}& \Leftrightarrow & y = mx + b
   \end{array}
\end{align}$$\\
<br>

$$\begin{align}
  \begin{array}{1}
  \text{Polynomial of degree 2}& \Leftrightarrow & \text{Quadratic polynomial}\\
  f(x) = a_{2}x^{2} + a_{1}x + a_{0}& \Leftrightarrow & f(x) = ax^{2} + bx + c, a \ne 0
   \end{array}
\end{align}$$\\
<br>

---
<br>
Functions are **even** when $f(-x) = f(x)$\\
When a negative $x$ value is inputted, the returned result is the same as though a positive $x$ value was inputted.\\
In a two-dimensional cartesian plot, $f(x)$ is symmetric about the $y$ axis, like $x^{2}$.

Functions are **odd** when $f(-x) = -f(x)$\\
When a negative $x$ value is inputted, the returned result is the same as the negative of a postive $x$ value inputted.\\
In a two-dimensional cartesian plot, $f(x)$ is symmetric about the $x$ axis, like $x^{3}$
<br>

---
<br>
The **zero** of a function $f$ is a number $x$ such that $f(x) = 0$\\
The zero is also known as the root.\\
The zero is the input number which makes the function $f(x)$ return zero.
In a two-dimensional cartesian plot, a zero would be an $x$ intercept since $y = 0$

The **intermediate value theorem**:\\
let $a$ and $b$ be real numbers : $a < b$\\
let $f$ be a polynomial function : $f(a) \ne f(b)$\\
In the interval $[a,b]$, $f$ returns every possible value between $f(a)$ and $f(b) inclusive$\\
$f(a)$ and $f(b)$ have opposite signs $\rightarrow f$ has a zero in the interval $[a, b]$