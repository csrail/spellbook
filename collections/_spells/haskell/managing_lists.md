---
layout: spell
date: 22-01-2025
---

A list can be expressed as its first element and its remaining elements `(x:xs)`. The first element `x` of a list the head. While the remaining elements `xs` is the tail. Closure functions are applied to one element at a time, so thinking of a list in terms of its head and tail improves our ability to define the function. This utility becomes evident in recursive functions.

```haskell
head [1,2,3]
# returns 1

tail [1,2,3]
# returns [2,3]
```

<br>

---

<br>

The `(:)` cons operator prepends an element to a list, it has type `a -> [a] -> [a]`.

```haskell
# lists are constructed one element at a time
[1,2,3]

# is equivalent to
1: (2: (3: []))

# which is evaluated as
1: (2: [3])
1: ([2,3])
[1,2,3]
```

<br>

The `(++)` append list operator appends two lists together, it has type `[a] -> [a] -> [a]`.

```haskell
[1,2] ++ [3,4]

# evaluates to
[1,2,3,4]
```
