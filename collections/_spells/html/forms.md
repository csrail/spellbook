---
layout: spell
date: 14-11-2024
---

Forms are a text entry point to communicating with the backend.  Without forms, interaction with web applications would be limited to clickable elements.

<br>

The intent of a form --- its edge in relation to the user vertex and the web application vertex --- can be determined by its action and method:
- the `action` specifies the URL destination address to send the form data to
- the `method` specifies the HTTP request type

```html
<form action="" method="">

</form>
```

<br>

In a form, controls determine the type of information that is collected.

$\text{let $p \in$ forms}$\\
$\text{let $q \in$ controls}$\\
$\text{let $r \in$ declared inputs}$

$\text{let } r \subseteq q \subseteq p$

<br>

$\exists q : \|r\| \equiv 1 \rightarrow r\ \text{belongs to a singleton set particular to that}\ q$

```html
<!-- text -->
<input type="text">

<!-- textarea -->
<textarea></textarea>

<!-- email -->
<input type="email">

<!-- password -->
<input type="password">

<!-- date -->
<input type="date">

<!-- hidden -->
<input type="hidden">
```

<br>

$\exists q : \|r\| > 1 \rightarrow r\ \text{belongs to a partition particular to that}\ q$
```html
<!-- dropdown -->
<select>
  <option></option>
  <option></option>
</select>

<!-- checkboxes -->
<fieldset>
  <legend></legend>
  <ul>
    <li>
      <input type="checkbox"/>
    </li>
    <li>
      <input type="checkbox"/>
    </li>
  </ul>
</fieldset>

<!-- radiobutton -->
<fieldset>
  <legend></legend>
  <ul>
    <li>
      <input type="radio"/>
    </li>
    <li>
      <input type="radio"/>
    </li>
  </ul>
</fieldset>
```

<br>

---

<br>

$\text{let $r \in$ declared inputs}$\\
$\text{let $s \in$ labels}$\\
$\text{let $R(x,y) =$ $x$ is the label for the input $y$}$

$\forall r \exists s : R(r,s)$\\
$\forall s \exists r : R(r,s)$

The relation $R$ is symmetric: all inputs $x$ should have a label $y$, and all labels $y$ should have an input $x$.

<br>

$\text{let $r \in$ declared inputs}$\\
$\text{let $s \in$ labels}$\\
$\text{let $t \in$ attributes}$

$\text{let $T(x,y) =$ element $x$ has an attribute $y$}$

```html
<div>
    <label></label>
    <input>
</div>
```

<br>

$\forall r \exists t : T(r,t)$\\
$\forall s \exists t : T(s,t)$

The relation $T$ is anti-symmetric, all elements $x$ have an attribute $y$, if the element is an attribute and has an attribute, then that element must itself be an attribute.

```html
<div>
    <label for="A"></label>
    <input id="A" name="B" value="A">
</div>
```

<br>

---

<br>

$\text{let $p \in$ forms}$\\
$\text{let $u \in$ buttons}$\\
$\text{let $U(x,y) =$ form $x$ has a button $y$}$

$\forall p \exists u : U(p,u) \wedge u = \text{submit type}$

All forms must have a submit button.

```html
<form>
    <button type="submit"></button>
</form>
```

<br>

Auxillary buttons exist as well.

```html
<!-- Resets all input fields of the form -->
<form>
    <button type="reset"></button>
</form>
```

```html
<!-- Event Listeners can be added to this button -->
<form>
    <button type="button"></button>
</form>
```