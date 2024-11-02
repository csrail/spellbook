---
layout: spell
date: 25-10-2024
---

```python
# INSERTION-SORT(A)
for j in range(1, len(A)):
    key = A[j]
    i = j-1
    while i > 0 and A[i] > key:
        A[i+1] = A[i]
        i = i-1
    A[i+1] = key
```

The `j` loop invariant:
- **Initialisation:** The index starts at 1 and not 0 because the first element on its own is already sorted; we start at the second element to begin solving the problem.
- **Maintenance:** As long as `j` is within the bounds of the array, an iteration will begin. `j` increments after every complete iteration.
- **Termination:** `j` reaches the array's length, which means all elements must be sorted.
- **Responsibility:** 
  - Declares the `key` variable as the `j` interest value; the `key` is used for the initialisation and maintenance of the `while` loop; the `key` also enables in-place swapping to occur without forgetting the interest value.
  - `i` index enables insertion of `A[j]` into the `A[1...j-1]` sorted sequence 
  - Before the next iteration begins, the `key` is assigned to the `A[i+1]` interest location which is the index at which the `while` loop terminates.  The `i+1` interest index is required because with every complete iteration of the `while` loop, `i` is decremented.

<br>

The `while` loop invariant:
- **Initialisation:** the `i` index must be $\ge 1$ (an index which is not the first element), and the value `A[i]` greater than `key`.
- **Maintenance:** as long as `i` index is $\ge 1$ (does not represent the first element), and the element `A[i]` $>$ `key`, there must be unsorted elements; a new iteration begins.  `i` is decremented before every complete iteration.
- **Termination:** when `i` reaches 0 then the index is at the first element then it is already sorted.  When `A[i]` is $<$ `key` this means a new sorted sequence is established.
- **Responsibility:**
  - assigns the `A[i]` value to the `A[i+1] location`.  This starts the swap process to move elements up the sequence.  The final part of the swap process is completed outside the `while` loop.

<br>

```c#
// INSERTION-SORT(A)
for (int j = 2; j++; j < A.Length) {
    int key = A[j];
    int i = j - 1;
    while (i > 0 && A[i] > key) {
        A[i+1] = A[i];
        i--;
    }
    A[i+1] = key
}
```