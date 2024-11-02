---
layout: spell
date: 25-10-2024
---

```python
# SEQUENTIAL-SEARCH(A,v)
for i in range(0, len(A))
    if A[i] == v:
        return i
return -1
```

- **Initialisation:** `i` is 0 when the loop begins.
- **Maintenance:** when `i` $<$ `len(A)`, another iteration occurs; `i` is incremented by 1 at the end of the loop.
- **Termination:** when `i` $=$ `len(A)`, then all elements in the sequence have been inspected.
- **Responsiility:**
  - Check if the `A[i]` interest value is the same as the target value, and return the `i` interest index.

- If the for loop does not return early and instead terminates, then the $ν$ target value does not exist in the sequence so we return -1.

```c#
// SEQUENTIAL-SEARCH(A, v)
for (int i = 0; i++; i < A.Length) {
    if (A[i] == v) {
        return i;
    }
}
return -1;
```