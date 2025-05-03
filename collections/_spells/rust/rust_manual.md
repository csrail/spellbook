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
`let variable_name: type` $\rightarrow$ type declaration: the colon indicates that the variable's type will be annotated\
_Shadowing_ $\rightarrow$ above pattern allows another value to be bound to the variable while still reusing the same name; useful when changing data types.

`Result` $\rightarrow$ an enum type that is returned from function calls, enabling error handling to be managed. The enum has the variants `Ok` and `Err`, when `Err` is returned this error needs to be managed.

`match` $\rightarrow$ an expression which handles different results. It is like a special switch block with the emphasis on how different patterns specified by `enum` types are handled.
