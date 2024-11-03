---
layout: spell
date: 04-11-2024
---

Writing `console.log()` or `Console.WriteLine()` is not an effective nor exhaustive method for debugging a runtime.  Dissuade yourself from using this and instead use breakpoints.

Apply a breakpoint and run the program in debugging mode (as opposed to release mode) to start the debugging session.  When the breakpoint is reached use "Step into", to get a granular view of the execution; use "Step over" to pass over the block and move to the next block of execution.

Objects and their fields can be inspected readily under local and global variables.  Precede a method call with `return` in order to record the return value in the debugger. 

The Debug Console tab can be used to evaluate expressions during the debugging runtime.  Read operations will occur without affecting the state of the runtime, but write operations will obviously change the state.