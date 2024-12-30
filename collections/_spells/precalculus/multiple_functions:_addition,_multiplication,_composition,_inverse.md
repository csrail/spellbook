---
layout: spell
date: 30-12-2024
---

Adding functions is commutative:
- $(f + g)(x) = f(x) + g(x)$
- The sum $f + g$ evaluated at $x$, equals $f(x) + g(x)$

<br>

Multiplying functions is commutative:
- $(fg)(x) = f(x)g(x)$
- The product $f * g$ evaluated at $x$, equals $f(x)g(x)$

<br>

---

<br>

Composing functions, evaluating one function and then afterwards evaluating a different function.  Therefore composition is not commutative:
- $f \circ g(x) = f(g(x))$
- The composition $f$ with $g$ equals $f(g(x))$

- $f \circ g(x)\ \text{in general} \ne g \circ f(x)$ 
- $f$ composed with $g$, in general, is not equal to $g$ composed with $f$.  This can be demonstrated by observing the differing domains of the composed functions.

<br>

---

<br>

Inverse functions:
- Let $f$ and $g$ be 2 functions:
  - $f(g(x)) = x, \forall x \in D: g$,
  - $g(f(x)) = x, \forall x \in D: f$
  - $\Rightarrow g$ is the inverse of $f$, denoted $f^{-1}$
- $(f$ is the inverse of $g)$ $\rightarrow$ $(g$ is the inverse of $f)$ 
  - $D : f \Leftrightarrow R : g$
  - $D : g \Leftrightarrow R : f$

<br>

- $f(f^{-1}(x)) = x$, $f^{-1}f((x)) = x$
- Verification: two functions are inverses of one another, when they are composed together, $x$ is always returned.
- $f$ composed with $f$ inverse of $x$ equals $x$, $f$ inverse composed with $f$ of $x$ equals $x$
  - $D : f \ \ \ \ \\Leftrightarrow R : f^{-1}$
  - $D : f^{-1} \Leftrightarrow R : f$
- The graphs of inverse functions are symmetric across the line $y = x$

<br>

Determining if a function has an inverse:
- A function can only have an inverse if and only if the function is **one-to-one**
- A function is one-to-one when it passes the **horizontal line test**, that is, that for every input, you get exactly one output that is not shared by any other input.
  - Suppose $f(x) = x^{2}$, $f(2) = 4$ and $f(-2) = 4$, then $f^{-1}(4)$ has two choices, therefore $f$ has no inverse.
- A function is one-to-one if, for $a$ and $b$ in the domain, $f(a) = f(b)$ implies $a = b$
  - Suppose $f(x) = x^{2}$, $f(a) = f(2) = 4$, and $f(b) = (-2) = 4$, but $a \ne b$