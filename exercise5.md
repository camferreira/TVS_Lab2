# Exercise 5

Consider the method
`doSomethingElse(int x, int y, int z, Stack aStack)`

whose domain satisfies the following constraints:

* x <= 0 && x <= y
* y < z;
* z <= aStack.size()
* !aStack.isFull()

Performing a domain analysis, design the test cases that verify the correct domain implementation for this method.

### Domain Analysis

- x <= 0
- x <= y
- y < z
- z <= aStack.size()
- !aStack.isFull()

### Baseline (valid case)

Use one valid combination and change one parameter at a time.
Baseline: `x = -1, y = 0, z=1, aStack.size()=2, aStack not full`

## Test cases

| TC | x  | y  | z | stack size | full? | Expected        |
| -- | -- | -- | - | ---------- | ----- | --------------- |
| 1  | -1 | 0  | 1 | 2          | no    | Valid           |
| 2  | 1  | 0  | 1 | 2          | no    | Invalid (x > 0) |
| 3  | -1 | -2 | 1 | 2          | no    | Invalid (x > y) |
| 4  | -1 | 1  | 1 | 2          | no    | Invalid (y ≥ z) |
| 5  | -1 | 0  | 3 | 2          | no    | Invalid (z > size) |
| 6  | -1 | 0  | 1 | 2          | yes   | Invalid (stack is full) |
| 7  | 0  | 0  | 1 | 1          | no    | Valid (boundary x = 0) |
| 8  | -1 | 0  | 2 | 2          | no    | Valid (boundary z = size) |
| 9  | -1 | 1  | 1 | 2          | no    | Invalid (boundary y = z) |