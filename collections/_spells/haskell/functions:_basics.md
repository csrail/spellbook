---
layout: spell
date: 21-12-2024
---

There are two components to defining functions:\\
$~ ~$The function's type definition.\\
$~ ~$The function's definition.

The type definition clarifies the particular inputs and outputs of the function. While the function definition shows us how the function is applied.

The type definition moves away from taking a tuple of arguments, to a sequence of arguments observed in curried functions. This type of abstraction helps us to see at each application of the function, the input received, and the output returned --- that is, the mapping of one type to another type. The type definition also makes precise the nature of the different types involved such as multiple polymorphic types represented as `a` and `b`, whether a list is being used as in `[a]` and `[b]`, or whether a function is being used as in `(a -> b -> a)`, denoted by round brackets.

The function definition takes multiple forms to satisfy various logical operations and more readable ways of expressing an idea. The representations can take the form of:

- pattern matching
- conditionals
- guard clauses
- lambda expressions
- operator sections
- list comprehensions
- recursive functions
- higher order functions

<br>

Pattern matching is the entry point into function definition. Patterns occur on the left side of the "equation" which represents the inputs that are expected, while the right side of the "equation" are the response outputs: how we want the function to transform the data's type.

```haskell
-- match on empty list
-- match on list with elements
head :: [a] -> a
head []     = []
head (x:xs) = x

-- since xs isn't used, this can be ommitted
-- by implementing wildcard pattern matching
head :: [a] -> a
head []    = []
head (x:_) = x
```

<br>

Conditionals enable branching. They take the form of `if <boolean> then <expression> else <expression>`. In conditionals, the `else` condition must be implemented.

<br>

Guard clauses place multiple `|` guards ahead of a final `otherwise` statement to be executed. Each guard is evaluated in sequence, and if there is a match then the return for that guard is immediate and no further evaluations occur. When all guards are evaluated and there are no matches, the final `otherwise` statement is always run.

<br>

Lambda expressions relate a function definition closer to its type definition. The `\` lambda enables a function to be defined in place so that readability is improved and indicating that a function is being returned.

<br>

Operator sections create functions that take an argument on its left in addition to the argument on its right. This increases the ability to express ideas since `1 + 1` is more intuitive than `+ 1 1`. The value of this expressibility can be observed in recursion and higher order funcions.

<br>

List comprehensions draw upon the idea of set theory where a subset is generated from a set. Elements are drawn from an initial list based on an optional filter, and optionally transformed, before being placed in the collecting list. The idea of expressing how a subset is taken from a set is useful, however, sets and lists cannot strictly be used interchangeably since sets are unordered and lists are ordered.

```haskell
squareEvens :: [Int] -> [Int]
--             = [transform | drawing from set, filter]
squareEvens xs = [x^2 | x <- xs, even x]

-- the <- drawing action should be the first consideration:
-- the element is drawn from the set

-- the filter should be the second consideration:
-- the filter must evaluate to a Boolean
-- True keeps the element, False discards the element

-- the transformation should be the third and final consideration:
-- if there is no transformation, record the element as it is
-- if there is a transformation, apply the transformation as needed

-- when all the above has taken place, a new set is formed, a subset of the set

takeEvens :: [Int] -> [Int]
--           = [no transformation | drawing from set, predicate]
takeEvens xs = [x | <- xs, even x]
```
