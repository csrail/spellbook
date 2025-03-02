---
layout: spell
date: 09-02-2025
---

"Cargo is Rust's build system and package manager."

```shell
# initialise a new project
$ cargo new project_name
```

Within the project root directory:

```shell
# checks whether the program can be compiled before committing resources
# for the compilation
$ cargo check

# compiles a debug program at ./target/debug/
$ cargo build

# runs the debug program located at ./target/debug/
$ cargo run

# builds a release version of the program at ./target/release
# the compile time is longer than the debug build, but there
# are optimisations in place to make execution of the program faster
$ cargo build --release
```
