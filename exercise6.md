# Exercise 6

Consider the method
`doSomething(float x, int y, float z)`
whose domain satisfies the following constraints:

* x > 1 && x <= 50;
* y > 1 && y <= 50
* x+y <= z
* z > 0 && z < 30

Performing a domain analysis, design the test cases that verify the correct domain implementation for this method.

### Domain Analysis

- x > 1
- x <= 50
- y > 1
- y <= 50
- x + y <= z
- z > 0
- z < 30

### Baseline (valid case)

Use one valid combination and change one parameter at a time.
Baseline: `x = 2, y = 2, z=5`

## Test cases

| TC | x  | y  | z  | Expected |
|----|----|----|----|----------|
| 1  | 2  | 2  | 5  | Valid |
| 2 | 1  | 2  | 5  | Invalid (x ≤ 1) |
| 3 | 51 | 2  | 60 | Invalid (x > 50) |
| 4 | 2  | 1  | 5  | Invalid (y ≤ 1) |
| 5 | 2  | 51 | 60 | Invalid (y > 50) |
| 6 | 2  | 2  | 0  | Invalid (z ≤ 0) |
| 7 | 2  | 2  | 30 | Invalid (z ≥ 30) |
| 8 | 2  | 2  | 3  | Invalid (x + y > z) |
| 9  | 2  | 2  | 4  | Valid (boundary x + y = z) |
| 10 | 2  | 2  | 5  | Valid (just above boundary) |
| 11 | 2  | 2  | 3.9| Invalid (just below boundary) |