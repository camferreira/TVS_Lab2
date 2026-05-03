# Exercise 2

Consider the following method

`int f (int x, int a, int b){...}`

that receives three parameters and performs a given processing. The x parameter must belong to the interval [a,b], a should be a positive number, and b cannot exceed 1000. Assume furthermore that an exception is raised if f is called with invalid parameters.

Perform a domain analysis and design the test cases that verify the implementation of this method.

### Domain Analysis

- x >= a
- x <= b
- a > 0
- b <= 1000

### Baseline valid values (control case)

Use one valid combination and change one parameter at a time.
Baseline: `x=3, a=1, b=5`

## Test cases (domain / boundary analysis)

| Test Case | x | a | b    | Expected |
| --------- | - | - | ---- | -------- |
| 1         | 3 | 1 | 5    | Valid    |
| 2         | 1 | 1 | 5    | Valid (x = a boundary) |
| 3         | 0 | 1 | 5    | Exception (x < a) |
| 4         | 5 | 1 | 5    | Valid (x = b boundary) |
| 5         | 6 | 1 | 5    | Exception (x > b) |
| 6         | 3 | 0 | 5    | Exception (a ≤ 0) |
| 7         | 3 | 1 | 1000 | Valid (upper boundary of b) |
| 8         | 3 | 1 | 1001 | Exception (b > 1000) |
| 9         | 3 | 5 | 1    | Exception (invalid interval a > b) |
