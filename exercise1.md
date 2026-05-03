# Exercise 1

`int doSomething(int a, int b, String str, Integer vec)`

### Domain Analysis

* a > 0
* b > 2
* b <= 200
* str != null
* str.length() >= 2
* vec.intValue() > 15

### Baseline valid values (control case)
Use one valid combination and change one parameter at a time.
Baseline: `a=1, b=3, str="ab", vec=16`

## Test cases (domain / boundary analysis)

| TC | a | b | str  | vec | Expected |
|---:|--:|--:|------|----:|----------|
| 1  | 1 | 3 | "ab" | 16  | Valid |
| 2  | 0 | 3 | "ab" | 16  | Invalid (violates `a > 0`) |
| 3  | 1 | 2 | "ab" | 16  | Invalid (violates `b > 2`) |
| 4  | 1 | 3 | "ab" | 16  | Valid (just above lower bound for `b`) |
| 5  | 1 | 200 | "ab" | 16 | Valid (upper bound included) |
| 6  | 1 | 201 | "ab" | 16 | Invalid (violates `b <= 200`) |
| 7  | 1 | 3 | null | 16  | Invalid (violates `str != null`) |
| 8  | 1 | 3 | ""   | 16  | Invalid (violates `str.length() >= 2`) |
| 9  | 1 | 3 | "a"  | 16  | Invalid (violates `str.length() >= 2`) |
| 10 | 1 | 3 | "ab" | 16  | Valid (length boundary satisfied) |
| 11 | 1 | 3 | "ab" | 15  | Invalid (violates `vec.intValue() > 15`) |
| 12 | 1 | 3 | "ab" | 16  | Valid (just above boundary for `vec`) |
