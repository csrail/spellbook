---
layout: spell
date: 13-11-2024
---

It is with complete (and productive) certainty that when developing and designing web applications, form follows function.

$\text{let $p =$ web application}$

$\text{let $q =$ web page}$

$\text{let $r =$ web component $:$ web component $\Leftrightarrow$ smallest functional unit}$

$\text{let } r \subseteq q \subseteq p$

When working on $r$, the focus should be on its semantic structure in isolation to all other web components.  On the surface $r$ will look like a clumsy heap, but so long as the semantic structure is sound, the styling will follow naturally.  Therefore, only attend to css when it is necessary for logical flow, otherwise, defer the styling (e.g. layout, sizing, colour) until the whole logical sequence is established.
