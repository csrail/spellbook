---
layout: spell
date: 20-12-2024
---

A **type** is a set of common values related by intrinsic properties.  The type specifies what sort of data we are looking so that we can apply operations to them.  A single element may exist as a basic or primitive type like `Int`, `Char` and `String`.  These elements can then be collected into a set, which itself is a type.  These sets come in two types: lists and tuples.

<br>

List types take the form `[]`, may only contain a single data type, but can have any number of elements.

```shell
# using ghci
:type ['1','2','3'] # returns [1,2,3] :: [Char]
```

Tuple types take the form `()`, may contain any data type, but must have the predefined number of ordered elements.  A tuple with two values can be called a pairing or an ordered pair.  A tuple with three values can be called a triplet etc.

```shell
# using ghci
:type (1, False) # returns (Int, Bool)
```

A list can contain a tuple:
```shell
# using ghci
:type [('S',True),('N',False)] # returns [('Char', Bool)]
```

<br>

A **function** type, is a mapping of one type to another type.  A function takes a single input and returns a single output.

A simple `multiply` function is examined:

```haskell
-- multiply is a function type which has a type which
-- takes a single argument, a tuple triplet of Int, Int and Int,
-- then returns a value of type Int
multiply :: (Int,Int,Int) -> Int
multiply (x,y,z) = x*y*z
```

A curried function of `multiply`:

```haskell
-- multiply is a curried function of type Int
-- multiply take an input Int and returns the function multiply Int
-- multiply Int takes an input Int and returns the function multiply Int Int
-- multiply Int Int takes an input Int and returns a value with type Int
-- the multiply function is bound so that given input x, input y, and input z, we perform the following: x + y + z
multiply :: Int -> Int -> Int -> Int
multiply x y z = x*y*z
```

Further analysis of the curried function:

```haskell
-- in the type definition, the arrow is associated to the element on its right
-- therefore the parentheses begin the association from right to left
multiply :: Int -> (Int -> (Int -> Int))
multiply x y z = ((x * y) * z)
-- but in the execution of the function,
-- the function is applied to the element on its right
-- therefore the parenthesis begin the association from left to right
(((multiply x) y) z)
```

Both multiply functions produce the same output.  However since the curried function returns a function in its intermediate outputs, when the function is applied onto an element, that is, we observe partial application of the function, then a more focussed and specialised version of the function can be declared.

<br>

---

<br>

Polymorphic functions.  A value in a definition can take on any type, but once that type is instantiated, must be maintained across the whole function definition.

```haskell
-- This function types demonstrates polymorphism;
-- the elements described in lowercase letters in the type definitions can take on any type
-- once the type is instantiated, the type must be maintained across the whole function definition
pair :: a -> b -> (a,b)
pair a b = (a,b)
```

Overloaded functions can be applied to types that are compositionally very similar.  A single type that collects many related types is called a class.  The class imparts functional meaning.  For example, the types `Int`, `Integer`, `Float` and `Double` are all Numeric `Num` types.

```haskell
-- This function type relates these three ideas:
-- the class, Num
-- polymoprhism, a
-- overloading, Num a
double :: Num a => a -> a
double x = x*2
```

The class applies a constraint to the polymorphic type, which subsets itself from all types to create an overloaded function.