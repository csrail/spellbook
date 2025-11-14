---
layout: spell
date: 09-02-2025
---

"Cargo is Rust's build system and package manager."

```shell
# initialise a new project
cargo new project_name
```

<br>

Within the project root directory:

```shell
# checks whether the program can be compiled before committing resources
# for the compilation
cargo check

# compiles a debug program at ./target/debug/
cargo build

# runs the debug program located at ./target/debug/
cargo run

# builds a release version of the program at ./target/release
# the compile time is longer than the debug build, but there
# are optimisations in place to make execution of the program faster
cargo build --release

# remove dependencies not listed in cargo.toml file
cargo clean
```

<br>

Code Management

```shell
# check what format changes will take place when calling `cargo fmt`
cargo fmt --check

# formats rust code to a sensible code style; should be run often while
# writing code to maintain the standard
cargo fmt

# parses code checking where improvements can be made;
# a succinct version of clippy is run during compilation
cargo clippy
```

```rust
// include this at the top of main.rs file to change clippy's mode
// from normal to pedantic
#![warn(clippy::all, clippy:pedantic)]
```

<br>

Dependency Management. Versioning follows the format:

- `[[major]].[[minor]].[[patch]]`
- major version increments when features added break compatibility changes
- minor version incremenets when features are added but maintain compatibility
- patch version increments when bug fixes added