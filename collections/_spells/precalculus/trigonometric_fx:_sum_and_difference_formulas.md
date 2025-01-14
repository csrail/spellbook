---
layout: spell
date: 14-01-2025
---

The sine of a sum of two angles is not the sum of the sines.\\
$~ ~$A $\sin{t},~ t = u\pm v : \sin{(u \pm v)}$ cannot be evaluated as $\sin{u} \pm \sin{v}$ since this would break $u$ and $v$ out of the function's execution, subverting logical operations.\\
$~ ~$Summation and differences of values within trigonometric functions can be resolved through trigonometric functions applied onto the constituent addends and subtrahends of $t$.

<br>

The function application for sine:\\
$~ \sin{(u \pm v)} = \sin{u}\cos{v} \pm \cos{u}\sin{v}$\\
The sine of $u$ plus minus $v$ equals the sine of $u$ times cosine $v$, plus minus cosine $u$ times sine $v$.\\
The sine of $u$ plus minus $v$ equals the sine of the first, times the cosine of the second, plus minus cosine of the first times sine of the second.

<br>

The function application for cosine:\\
$~ \cos{(u \pm v)} = \cos{u}\cos{v} \mp \sin{u}\sin{v}$\\
The cosine of $u$ plus minus $v$ equals the product cosine $u$ times cosine $v$ **minus plus** the product sine $u$ times sine $v$\\
The cosine of $u$ plus minus $v$ equals the product cosine of the first times cosine of the second **minus plus** the product sine of the first times sine of the second.

<br>

The function application for tangent:\\
$\displaystyle~ \tan{(u \pm v)} = \frac{\tan{u}\pm\tan{v}}{1 \mp \tan{u}\tan{v}}$\\
$~ ~$The tangent of $u$ plus minus $v$ is equal to the tangent of $u$ plus minus the tangent of $v$ over one **minus plus** the tangent of $u$ times the tangent of $v$\\
$~ ~$The tangent of $u$ plus minus $v$ is equal to the tangent of the first plus minus the tangent of the second over one **minus plus** the tangent of the first times the tangent of the second.

<br>

---

<br>

## Conceptualisation
Let $u = b = \text{base}$\\
Let $v = c = \text{complement}$

<br>

Conceptualising the function application for sine:\\
$~ \sin{(u \pm v)} = \sin{u}\cos{v} \pm \cos{u}\sin{v}$\\
$\Leftrightarrow \sin{(u \pm v)} = \sin{u}\cos{v} \pm \sin{v}\cos{u}$\\
$\Leftrightarrow \sin{(b \pm c)} = \sin{b}\cos{c} \pm \sin{c}\cos{b}$\\
The sine of the base plus minus the complement equals the sine of the base, times the cosine of the complement, plus minus the sine of the complement times the cosine of the base.

This means the sine of the summation of the base and the complement can be thought of as the sine of the base being modified by the cosine of the complement, plus the sine of the complement being modified by the cosine of the base.

<br>

Conceptualising the function application for cosine:\\
$~ \cos{(u \pm v)} = \cos{u}\cos{v} \mp \sin{u}\sin{v}$\\
$\Leftrightarrow \cos{(b \pm c)} = \cos{b}\cos{c} \mp \sin{b}\sin{c}$\\
The cosine of the base plus minus the complement equals the product of the cosine of the base times the cosine of the complement, minus the product of the sine of the base times the sine of the complement.

This means the cosine of the summation of the base and the complement can be thought of as the product of cosine functions of the base and the complement, minus the product of the sine functions of the base and the complement.

<br>

Conceptualising the function application for tangent:\\
$\displaystyle~ \tan{(u \pm v)} = \frac{\tan{u}\pm\tan{v}}{1 \mp \tan{u}\tan{v}}$\\
<br>
$\displaystyle\Leftrightarrow~ \tan{(b \pm c)} = \frac{\tan{b}\pm\tan{c}}{1 \mp \tan{c}\tan{c}}$\\
$~ ~$The tangent of the base plus minus complement is equal to the tangent of the base plus minus the tangent of the complememnt over one **minus plus** the tangent of the base times the tangent of the complement.

This means the tangent of the summation of the base and the complement can be thought of as the  tangent of the base plus the tangent of the complement, multiplied by a factor that increases the magnitude of the result.\\
This means the tangent of the difference of the base and the complement can be thought of as the  tangent of the base minus the tangent of the complement, multiplied by a factor that decreases the magnitude of the result.

<br>

---

<br>

## Extension

Suppose the base and complement angles are the same: $u = v$.  Then you have a focus where $u + v = u + u = 2u$.

$\sin{(u + u)} = \sin{u}\cos{u} + \sin{u}\cos{u}$\\
$\Rightarrow \sin{(2u)} = \sin{u}\cos{u} + \sin{u}\cos{u}$\\
$\Rightarrow \sin{(2u)} = 2\sin{u}\cos{u}$

$\cos{(u + u)} = \cos{u}\cos{u} - \sin{u}\sin{u}$\\
$\Rightarrow \cos{(2u)} = \cos^{2}{u} - \sin^{2}{u}$

Given $\sin^{2}{u} + \cos^{2}{u} = 1 \Leftrightarrow \sin^{2}{u} = 1 - \cos^{2}{u}$, then:\\
$\cos{(2u)} = \cos^{2}{u} - \sin^{2}{u}$\\
$\Leftrightarrow \cos{(2u)} = \cos^{2}{u} - (1 - \cos^{2}{u})$\\
$\Leftrightarrow \cos{(2u)} = \cos^{2}{u} - 1 + \cos^{2}{u}$\\
$\Leftrightarrow \cos{(2u)} = 2\cos^{2}{u} - 1$

Given $\sin^{2}{u} + \cos^{2}{u} = 1 \Leftrightarrow \cos^{2}{u} = 1 - \sin^{2}{u}$, then:\\
$\cos{(2u)} = \cos^{2}{u} - \sin^{2}{u}$\\
$\Leftrightarrow \cos{(2u)} = 1 - \sin^{2}{u} - \sin^{2}{u}$\\
$\Leftrightarrow \cos{(2u)} = 1 - 2\sin^{2}{u}$