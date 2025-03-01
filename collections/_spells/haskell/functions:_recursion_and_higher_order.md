---
layout: spell
date: 23-01-2025
---

Recursion is the application of a function such that during its application, the function is applied onto a reduced set of its input. This function application expands, in relation to stack memory, only returning once the base case is reached. Recursion is readily expressed by using pattern matching and guard clauses. Pattern matching identifies the base cases (empty set or a single element) and the recursive case (the whole remaining set) to be managed. While the guard clauses specify what to return: for the base case, a finite value; for the recursive case, a recursion which moves towards the base case.

Closures are functions that return a function. Higher order functions are an extension of closures in that they return a function but also take functions as inputs. The mechanism of higher order functions creates and environment which encapsulates an arrangement of function patterns.

```haskell
# hof == higher order function
#   f == input function for the hof

# the first input for the hof is a function (a -> b) named 'f'
# the second input input for the hof is a list [a]
# the output for the hof is a list [b]

# the type definition of f are the components within the round brackets
# therefore function f takes input a, and outputs b
hof :: (a -> b) -> [a] -> [b]
hof f []   = []
hof f x:xs = f x : hof f xs
```

```haskell
# hof == higher order function
#   p == input function for the hof, specifically a predicate

# the first input for the hof is a function (a -> Bool) named 'p'
# the second input input for the hof is a list [a]
# the output for the hof is a list [a]

# the type definition of p are the components within the round brackets
# therefore the predicate takes input a, and outputs Boolean
hof :: (a -> Bool) -> [a] -> [a]
hof p xs = [x | x <- xs, p x]
```

<br>

---

<br>

The `foldr` fold right function demonstrates the encapsulation environment that higher order functions provide. `foldr` encapsulates recursive function definitions.

```haskell
# A simple recursive function
f :: [a] -> a
f [] = []
f (x:xs) = x # f xs

# is encapsulated in foldr
foldr :: (a -> b -> b) -> b -> [a] -> b
foldr f v []     = v
foldr f v (x:xs) = f x (foldr f v xs)
```

For example, the representation of a `[1,2,3]` list as a cons operation:

```haskell
# 1 : (2 : (3 : []))
# 1 : (2 : [3])
# 1 : ([2,3])
# [1,2,3]
```

Is represented in the `foldr` function as:

```haskell
foldr (:) [] [1,2,3]
# Is evaluated as
# (:) 1 (foldr (:) [] [2,3])
# (:) 1 ((:) 2 (foldr (:) [] [3]))
# (:) 1 ((:) 2 ((:) 3 (foldr (:) [] [])))
# (:) 1 ((:) 2 ((:) 3 (0)))
```

Thus for the given recursive function `recurseSum`, when using `foldr`, instead of thinking of the problem as a process of recursion, the process can be thought of as a cons operation, where the `(:)` operator is replaced by the `(+)` operator, and the `[]` empty list by `0`.

```haskell
recurseSum :: [a] -> a
recurseSum []     = 0
recurseSum (x:xs) = x + recurseSum xs

recurseSum [1,2,3]
# 1 + (recurseSum [2,3])
# 1 + (2 + (recurseSum 3))
# 1 + (2 + (3 + recurseSum []))
# 1 + (2 + (3 + (0)))
# 1 + (2 + (3))
# 1 + (5)
# 6
```

```haskell
foldr (+) 0 [1,2,3]
# clearest representation of the process whereby
# the (:) operator is replaced by the (+) operator
# the [] empty list replaced by the corresponding empty value
# 1 : (2 : (3 : ([]))
# 1 + (2 + (3 + (0)))

# Using the (+) operator intuitively between operands,
# but still not very clear
# 1 + (foldr (+) 0 [2,3])
# 1 + (2 + (foldr (+) 0 [3]))
# 1 + (2 + (3 + (foldr (+) 0 [])))
# 1 + (2 + (3 + (0)))

# Using the (+) operator as a function that takes arguments,
# difficult to understand.
# (+) 1 (foldr (+) 0 [2,3])
# (+) 1 ((+) 2 (foldr (+) 0 [3]))
# (+) 1 ((+) 2 ((+) 3 (foldr (+) 0 [])))
# (+) 1 ((+) 2 ((+) 3 0))
```

```haskell
recurseSum = foldr (+) 0
recurseSum [1,2,3]
```
