---
layout: spell
date: 23-10-2024
---

C Philosophy: conservation mechanism --- provide only one way to do an operation.

Header files are libraries pulled into the current file:
- `stdio.h` provides the C Standard I/O functions.
- `stdlib.h` provides utility functions

The main function is called at the program startup. It is declared with the return type `int` and takes no arguments (`void`).

```c
// DECLARE headers
#include <stdio.h> // provide access to puts function
#include <stdlib.h> // provide access to EXIT_SUCCESS macro

int main(void) {
    puts("Hello, world!"); // write to stdout
    return EXIT_SUCCESS; // macro evaluates to 0
}
```

Compile the source `hello.c` file into a `hello` binary file:

```bash
gcc -o hello hello.c
```
