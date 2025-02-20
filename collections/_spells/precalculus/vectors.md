---
layout: spell
date: 20-02-2025
# $\parallel PQ \parallel$
# $\|\| PQ \|\|$
# $\| PQ \|$
---

Quantities with a magnitude and a direction are represented as vectors, e.g. velocity, acceleration, force. Contrast this to quantities that only have a magnitude: temperature, weight, time.

A directed line segment $\overrightarrow{PQ}$ has an initial point $P$ and a terminal point $Q$.\\
The magnitude of the directed line segment $\overrightarrow{PQ}$ is $\lVert \overrightarrow{PQ} \rVert$.

<br>

A directed line segment becomes a vector when viewed in a coordinate plane:\\
$v = \overrightarrow{PQ}$\\
$u = \overrightarrow{RS}$

The vector $v$ has an initial point $P$ at $(0,0)$ and a terminal point $Q$ at $(2,3)$.\\
The vector $u$ has an initial point $R$ at $(1,1)$ and a terminal point $Q$ at $(3,4)$.

The vector $v$ has its initial point $P$ at the origin $(p_1,p_2)$.\\
$\Rightarrow$ this vector is in standard position\\
$\Rightarrow$ this vector can be described wholly by its terminal point $Q$ at $(q_1,q_2)$\\
$\Rightarrow$ these terminal points form the components of the vector $\langle v_1, v_2\rangle$ --- note the angled brackets

$\Rightarrow \overrightarrow{PQ} = \langle q_{1} - p_{1}, q_{2} - p_{2}\rangle$\\
$\Leftrightarrow \langle q_{1} - 0, q_{2} - 0\rangle$\\
$\Leftrightarrow \langle v_{1}, v_{2} \rangle$\\
$\Leftrightarrow v$

**Component form:**\\
$~~v = \langle v_{1}, v_{2} \rangle$

<br>

The magnitude of the vector is:\\
$\lVert v \rVert = \sqrt{~{v_1}^{2} + {v_2}^2}$.

$\lVert \overrightarrow{PQ} \rVert = \sqrt{(q_{1} - p_{1})^2 + (q_{2} - p_{2})^2}$\\
$\Rightarrow \sqrt{(2 - 0)^2 + (3 - 0)^2}$\\
$\Rightarrow \sqrt{2^2 + 3^2}$\\
$\Rightarrow \sqrt{4 + 9}$\\
$\Rightarrow \sqrt{13}$

$\lVert \overrightarrow{RS} \rVert = \sqrt{(s_{1} - r_{1})^2 + (s_{2} - r_{2})^2}$\\
$\Rightarrow \sqrt{(3 - 1)^2 + (4 - 1)^2}$\\
$\Rightarrow \sqrt{2^2 + 3^2}$\\
$\Rightarrow \sqrt{4 + 9}$\\
$\Rightarrow \sqrt{13}$

Direction and magnitude of the vectors $\overrightarrow{PQ}$ and $\overrightarrow{RS}$ are preserved so they are equivalent.
$\therefore~~ \overrightarrow{PQ} \Leftrightarrow \overrightarrow{RS}$

<br>
<br>

Vector Operations:

Addition:\\
$v + u$\\
$\Rightarrow \langle v_1, v_2 \rangle + \langle u_1, u_2 \rangle$\\
$\Rightarrow \langle v_1 + u_1, v_2 + u_2 \rangle$

Scalar Multiplication:\\
$k \cdot v, k \in \mathbb{R}$\\
$\Rightarrow \langle kv_1, kv_2\rangle$

<br>
<br>

Unit vectors have a magnitude of 1.

Standard unit vectors:\\
${\textbf i} = \langle 1,0 \rangle$\\
${\textbf j} = \langle 0,1 \rangle$

For a given vector $v$, to find its unit vector, divide the original vector $v$ by its magnitude $\lVert v \rVert$\\
$\Rightarrow$ multiply $v$ with the reciprocal of its magnitude $\lVert v \rVert$

$\displaystyle \Rightarrow \frac{1}{\lVert v \rVert} \cdot v$

$\displaystyle \Rightarrow \langle \frac{1}{\lVert v \rVert} v_1, \frac{1}{\lVert v \rVert} v_2\rangle$
<br>
<br>

**Trigonometric Form:**\\
Given the unit vector $u$:\\
$u = \langle 1,1 \rangle$\\
$\Rightarrow u = \langle 1,0 \rangle + \langle 0,1 \rangle$\\
$\displaystyle \Rightarrow u = \cos\theta \langle 1,0 \rangle + \sin\theta \langle 0,1 \rangle,$\\
$\displaystyle \Rightarrow u = \cos\theta {\textbf i} + \sin\theta {\textbf j},$\\
$\displaystyle ~~\cos\theta = x\ \text{direction},$\\
$\displaystyle ~~\sin\theta = y\ \text{direction}$

A vector $v$ based off the unit vector $u$ is:\\
$v = \lVert v \rVert (\cos\theta {\textbf i} + \sin\theta {\textbf j})$\\
$\displaystyle \Rightarrow v= \lVert v \rVert (\cos\theta {\textbf i}) + \lVert v \rVert (\sin\theta {\textbf j}),$\\
$\displaystyle ~~\cos\theta = x\ \text{direction},$\\
$\displaystyle ~~\sin\theta = y\ \text{direction},$\\
$\displaystyle ~~\lVert v \rVert = \text{scalar multiplier}$

$\displaystyle \Rightarrow v= a{\textbf i} + b{\textbf j},$\\
$\displaystyle ~~a = \lVert v \rVert \cos\theta = x\ \text{scaled direction},$\\
$\displaystyle ~~b = \lVert v \rVert \sin\theta = y\ \text{scaled direction}$
