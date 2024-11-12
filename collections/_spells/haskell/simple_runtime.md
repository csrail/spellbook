---
layout: spell
date: 06-11-2024
---

Only declarations can happen at the top level of the Haskell environment.  No method calls are allowed.  To work on a simple program, write the declarations as needed, then test the method by declaring main:

```haskell
-- product.hs file
-- multiples a sequence of numbers returning a single output value
myProduct [] = 1
myProduct (n:ns) = n * myProduct ns

main = print (myProduct [2,3,4])
```

Then load the file into the haskell interpreter:

```shell
ghci product.hs

main
```

If the file is changed during the interactive session, you can reload the interpreter:

```shell
:reload
```

If the command is unique, the first letter will do:
```shell
# same as :reload
:r 
```