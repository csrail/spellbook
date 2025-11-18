---
layout: spell
date: 18-11-2025
---

Calculus is a branch of mathematics consolidated by Gottfried Wilhelm Leibniz (1646--1716) and Isaac Newton (1642--1727).

Calculus describes the mathematics of change.   Where there is a change in a variable over time, the observed change can be computed coarsely, as in the **average** change in the variable. Or, the observed change can be computed precisely, asin the **instantaneous** change in the variable.

If we relate this principle to velocity, then there is the coarse average velocity, and the instantaneous velocity.

<br>

There is differential calculus and integral calculus.  Both types are two sides of the same coin.

A rudimentary way of understanding differential calculus is to explore the tangent line problem.  Given the graph $y = x^2$ we have the point $P (2,4)$ which we want to calculate the slope of the tangent line for. An estimate of the tangent line slope could be calculated using a neighbouring point $Q (3,9)$, such that

$\displaystyle m = \frac{\Delta y}{\Delta x} = \frac{y_2 - y_1}{x_2 - x_1} = \frac{9-4}{3-2} = \frac{5}{1}$

The slope of this secant line, is far too crude an estimate of the tangent line slope.  We can generalise point $Q$ to $(x, x^2)$ instead.  Then so long as the x value of point $Q$ is not $2$ (to avoid 0 in the denominator), as point $Q$ moves closer to point $P$, a closer approximation of the tangent line slope can be achieved.   Therefore the slope of the secant line closely approaches the tangent line.  When we choose closer and closer $x$ values for point $Q$ that approach from the positive and the negative direction, then we find the limit of $x$ to calculate the target slope.  We can then take the limit of $x$ approaching $2$ to find the slope at the precise point of interest, point $P$:

$\displaystyle\lim_{x\rightarrow 2} \frac{x^2 - 4}{x - 2} = \lim_{x\rightarrow 2} \frac{(x+2)(x-2)}{x-2} = \lim_{x\rightarrow 2} (x+2) = 4$

<br>

Applying the point-slope formula, we can obtain the equation of the exact tangent line that intersects point $P (2, 4)$ with a slope of $4$:

$y - y_1 = m(x - x_1)$\
$y - 4 = 4(x - 2)$\
$y - 4 = 4x - 8$\
$y = 4x - 4$

<br>

## Exercises

Find the equation of the tangent line to parabola $y = x^2$ at the point $(3,9)$

$\displaystyle \text{gradient} = \lim_{x\rightarrow 3} \frac{x^2 - 9}{x - 3} = \lim_{x\rightarrow 3} \frac{(x+3)(x-3)}{x-3} = \lim_{x\rightarrow 3} x+3 = 6$

Point-slope formula substituting values point $(3,9)$ with gradient $6$:\
$y - y_1 = m(x - x_1)$\
$y - 9 = 6(x - 3)$\
$y - 9 = 6x - 18$\
$y = 6x - 9$

<br>

Find the equation of the tangent line to the cubic polynomial $y = x^3$ at the point $(-1,-1)$

Gradient:\
$\displaystyle= \lim_{x\rightarrow -1} \frac{x^3 - -1}{x - -1}$

$\displaystyle= \lim_{x\rightarrow -1} \frac{x^3 + 1}{x+1}$

$\displaystyle = \lim_{x\rightarrow -1} \frac{(x+1)(x^2 -x +1)}{x+1}$

$\displaystyle = \lim_{x\rightarrow -1} x^2 - x + 1$

$\displaystyle = \lim_{x\rightarrow -1} (-1)^2 - (-1) + 1$

$= 3$

Point-slope formula substituting values point $(-1,-1)$ with gradient $3$:\
$y - y_1 = m(x - x_1)$\
$y - -1 = 3(x - -1)$\
$y + 1 = 3x + 3$\
$y = 3x + 2$
