# Exercise 4

Consider a method
`doSomething(float x, int y)`
whose domain satisfies the following constraints:

- x > 1 && x <= 12;
- y <= 12 && y > 1;
- y < 8 - x/2

Performing a domain analysis, design the test cases that verify the correct domain implementation for this method.

### Domain Analysis

- x > 1
- x <= 12
- y <= 12
- y > 1
- y < 8 - x/2

Equivalent constraint:
- x < 16 - 2y

### Baseline (valid case)

Use one valid combination and change one parameter at a time.
Baseline: `x = 2, y = 3`

## Test cases

| TC | x  | y  | Expected                           |
| -- | -- | -- | ---------------------------------- |
| 1  | 2  | 3  | Valid                              |
| 2  | 1  | 3  | Invalid (violates `x > 1`)       |
| 3  | 12 | 3  | Valid                              |
| 4  | 12 | 3  | Invalid (violates `y < 8 - x/2`) |
| 5  | 13 | 3  | Invalid (violates `x ≤ 12`)     |
| 5  | 2  | 1  | Invalid (violates `y > 1`)       |
| 6  | 2  | 12 | Invalid (violates `y < 8 - x/2`) |
| 7  | 2  | 13 | Invalid (violates `y ≤ 12`)     |
| 8  | 2  | 7  | Invalid (boundary `y = 8 - x/2`) |
| 9  | 2  | 6  | Valid (just below boundary)        |

### Notes

- Boundary for `x`: 1 / 2 and 12 / 13
- Boundary for `y`: 1 / 2 and 12 / 13
- Dynamic boundary: `y = 8 - x/2`
