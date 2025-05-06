---
layout: spell
date: 03-05-2025
---

## Summaries

### Chapter 1: Environment setup

### Useful

#### Basics

`rustup docs` opens up a listing of documentation.

`rustc main.rs` compiles the main file.

`./main` executes the compiled file.

#### Cargo

When [Cargo initialises a new project:](/spellbook/spells/rust/cargo.html)\
$\rightarrow$ git is initialised\
$\rightarrow$ source files located under `src/`\
$\rightarrow$ compiled files located under `target/`\
$\rightarrow$ cargo configuration file initialised as `Cargo.toml`

### Archive

`cargo` $\rightarrow$ Rust's build system and package manager. Handles compilation and installing dependencies.

`rustup` $\rightarrow$ manager for Rust language and its toolchain.

`xcode-select --install` $\rightarrow$ installs a C compiler and linker. The linker joins compiled outputs into one file for use.

`rustc --version` checks Rust is installed.

`rustup update` updates the package manager.

<br>

### Chapter 2: Basic Program demonstration

Crates $\rightarrow$ a collection of Rust source code files

- Binary crate $\rightarrow$ the executable program being developed.
- Library crate $\rightarrow$ code to be used as source code in other programs, cannot be executed on its own.

`prelude` $\rightarrow$ library that is automatically brought into scope for every program\
`use` $\rightarrow$ keyword to bring other libraries into scope

[`Cargo.toml`](https://toml.io/en/) $\rightarrow$ configuration file that manages dependencies.\
[Semantic Versioning](https://semver.org) $\rightarrow$ specification for dependency versioning.

`let mut variable_name = String::new()` $\rightarrow$ `=` binds the RHS to the LHS\
`let variable_name: type` $\rightarrow$ type declaration: the colon indicates that the variable's type will be annotated

`Result` $\rightarrow$ an enum type that is returned from function calls, enabling error handling to be managed. The enum has the variants `Ok` and `Err`, when `Err` is returned this error needs to be managed.

`match` $\rightarrow$ an expression which handles different results. It is like a special switch block with the emphasis on how different patterns specified by `enum` types are handled.

<br>

### Chapter 3: Logic flow, Memory management

#### variables, mutability

variables by default are immutable $\rightarrow$ encourages code that focuses on safety and concurrency\
`mut` $\rightarrow$ informs the compiler that this variable will change value over time, as opposed to other language where this specification is implicit so the variable changes sometimes

constants $\rightarrow$ always immutable, value does not change once set, value must be set at compilation time not at runtime, <u>type must always be specified</u>

```rust
const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```

_Shadowing_ $\rightarrow$ allows another value to be bound to the variable while still reusing the same name; useful when changing data types such as when applying a transformation to the data and then maintaining immutability afterwards

```rust
let spaces = "   "; // String type, immutable
let spaces = spaces.len(); // transformation, integer type, immutability maintained
```

```rust
// c.f compile error when trying to use mutability while changing type:
let mut spaces = "   "
spaces = spaces.len() // cannot change type like this -> maintain type safety
```

<br>

#### data types

_statically typed language_ $\rightarrow$ types of all variables must be be known at compile time

**scalar types** $\rightarrow$ represents a single value\
$\rightarrow$ integers\
$\rightarrow$ floating-point\
$\rightarrow$ numbers\
$\rightarrow$ Boolean\
$\rightarrow$ characters

_integer type_ $\rightarrow$ numbers without a fractional component

_unsigned integer_ $\rightarrow$ ranges from $[0, 2^n - 1]$\
e.g. `u8` is a unsigned 8-bit integer $\rightarrow [0, 2^8 -1] \rightarrow$ $[0,255]$

_signed integer_ $\rightarrow$ ranges from $[-2^{n-1}, 2^{n-1} - 1]$, stored using two's complement\
e.g. `i8` is a signed 8-bit integer $\rightarrow [-2^{8-1}, 2^{8-1} - 1] \rightarrow [-2^{7}, 2^{7} -1] \rightarrow [-128,127]$

_integer overflow_ $\rightarrow$ counting a number that exists beyond the memory allocated\
$\Rightarrow$ two's complement wrapping will occur by default but this is considered an error,\
manage by special handling:\
$\rightarrow$ `wrapping_*` methods\
$\rightarrow$ `checked_*` methods\
$\rightarrow$ `overflowing_*` methods\
$\rightarrow$ `saturating_*` methods

_floating point type_ $\rightarrow$ numbers with decimal points\
$\rightarrow$ all floating points are signed\
$\rightarrow$ `f32` and `f64` $\Rightarrow$ `f64` by default because roughly same speed and greater precision than `f32`

_boolean type_ $\rightarrow$ one byte in size, `bool` is `true` or `false`

_char type_ $\rightarrow$ four bytes in size, `char` represents a Unicode Scalar Value

_Unicode Scalar Value_\
$\rightarrow$ ranges from [`U+0000`,`U+D7FF`]\
$\rightarrow$ AND ranges from [`U+E000`,`U+10FFF`]

**compound types** $\rightarrow$ group multiple values into one type\
two primitive compound types:\
$\rightarrow$ tuples\
$\rightarrow$ arrays

_tuple type_ $\rightarrow$ group values of different types together\
$\rightarrow$ cannot grow or shrink in size once declared\
$\rightarrow$ expressions that do not specify a return value implicitly return a _unit_ i.e. an empty tuple `()`

```rust
// type delcaration and initialisation
let tup: (i32, f64, u8) = (500, 6.4, 1);

// destructuring
let (x, y, z) = tup; // x <- 500, y <- 6.4, z <- 1

// access by index
let five_hundred = tup.0;
let six_point_four = tup.1;
let one = tup.2;
```

_array type_ $\rightarrow$ group values of the same type together\
$\rightarrow$ has a fixed number of elements c.f. _vector type_ which is a collection that can grow or shrink in size\
$\rightarrow$ useful when allocating data to the stack instead of the heap

```rust
// specification of type and then size
let a: [i32; 5] = [1, 2, 3, 4, 5];

// initialise array with the same element
let b = [0; 5];
// is the same as
let b = [0,0,0,0,0];

// access by index
let first = a[0]
let second = a[1]
```

_index out of bounds_ $\rightarrow$ a runtime error that occurs when attempting to access an index value outside of the possible indices; Rust will exit the program with this error\
$\Rightarrow$ memory safety\
$\rightarrow$ c.f. in lower level langagues, invalid memory can be accessed.

<br>

#### functions

`snake_case` $\rightarrow$ to write function names and variable names

`fn` keyword to define a function; as long as the function is defined in the same scope that can be seen by the caller.\
$\rightarrow$ add `->` after the parameter declarations and before the curly bracket to specify the return type.

_parameter declarations_ $\rightarrow$ specification of the function's signature where type must be specified; the type annotations informs the compiler about the arguments that can be passed to the function.

_statements_ $\rightarrow$ instructions that perform an action but do not return a value $\Rightarrow$ end with a `;`\
$\rightarrow$ defining a function is a statement\
$\rightarrow$ assignments are a statement

_expressions_ $\rightarrow$ evaluate to a resultant value $\Rightarrow$ do not end with a `;`
$\rightarrow$ calling a function is an expression\
$\rightarrow$ calling a macro is an expression\
$\rightarrow$ a value is an expression\
$\rightarrow$ creating a new scope block with curly braces is an expression

<br>

#### control flow

`if` conditional $\rightarrow$ expects an explicit `bool` type and non-Boolean types are not implicitly converted to a Boolean type like in Ruby or Javascript.

`match` $\rightarrow$ a branching construct which supersedes multiple `else if` statements.

_conditional assignment_ $\rightarrow$ conditionally assign a value to a variable; follows a ternary operation?

```rust
let condition = true;
// 5 is assigned to number
// note types returned in the if and else arms must be the same
let number = if condition { 5 } else { 6 };
```

`break` $\rightarrow$ exits the current loop\
$\rightarrow$ possible to return a value e.g. `break x;`

`continue` $\rightarrow$ skip remaining code in the loop and go to next iteration of the loop

`return` $\rightarrow$ exits the current function to return a value (all loops foregone).

named loops $\rightarrow$ enables break to apply to a loop outside the current loop.

```rust
'outer_loop: loop {
    // other statements executed
    loop {
        // inner loop statements executed
        break 'outer_loop
    }
}
```

`while` $\rightarrow$ a construct which pieces together `loop`, `if`, `else` and `break` in a nicer format

`for` $\rightarrow$ executes code for each item of a collection; safer than `while` construct as it avoids index out of bounds; faster than a `while` construct since the conditional does not need to be evaluated

`for` with `Range` $\rightarrow$ iterate loop for a given number of times

### Chapter 4: Ownership
