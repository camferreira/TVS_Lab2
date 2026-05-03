# Exercise 7

Consider method
`int[] compute(int x, int y)`
whose responsibility is to return the multiples of x that are smaller than or equal to y. If there are none, then the returned vector should have size  0. Consider also the following restrictions on x and y:

* y has to be greater than x, otherwise throws exception InvalidNumberException.
* both x and y can only have positive values, throwing the exception InvalidNumber otherwise.

Apply the most suitable test pattern to determine the test suite that checks the correct behavior of this method.

### Domain

- x > 0  
- y > 0  
- y > x  

---
## Test Pattern

Input Domain Partitioning + Boundary Value Analysis

---

## Baseline (valid case)

Use one valid combination and change one parameter at a time.
Baseline: `x = 2, y = 10 → [2, 4, 6, 8, 10]`

## Test cases

| TC | x  | y  | Expected |
|----|----|----|----------|
| 1  | 2  | 10 | [2, 4, 6, 8, 10] |
| 2  | -1 | 10 | Exception (x ≤ 0) |
| 3  | 2  | -5 | Exception (y ≤ 0) |
| 4  | 5  | 5  | Exception (y ≤ x) |
| 5  | 6  | 5  | Exception (y < x) |
| 6  | 2  | 3  | [2] (boundary: y = x + 1) |
| 7  | 2  | 2  | Exception (boundary y = x) |
| 8  | 3  | 4  | [3] |
| 9  | 3  | 10 | [3, 6, 9] |


### Notes

- Boundary for `x`: 0 / 1  
- Boundary for `y`: x / x+1  
- For all valid inputs (y > x), the result is never empty, since x is always a multiple of itself and x ≤ y.
Therefore, the case of an empty vector is unreachable under valid inputs.


---
# Another Solution

## Test Pattern

Output-based Partitioning (Behavior-based testing)

---

## Behavioral Partitions

### Valid behavior
- Multiple values returned  
- Single value returned  
- Upper bound included (y is a multiple of x)  

### Invalid behavior
- x ≤ 0  
- y ≤ 0  
- y ≤ x  

---

## Test cases

| TC | x  | y  | Expected |
|----|----|----|----------|
| 1  | 2  | 10 | [2, 4, 6, 8, 10] (multiple values) |
| 2  | 3  | 4  | [3] (single value) |
| 3  | 5  | 15 | [5, 10, 15] (y is multiple of x) |
| 4  | -1 | 10 | Exception (x ≤ 0) |
| 5  | 2  | -5 | Exception (y ≤ 0) |
| 6  | 5  | 5  | Exception (y ≤ x) |
| 7  | 6  | 5  | Exception (y < x) |