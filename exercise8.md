# Exercise 8

Consider the method void `push(Object element)` of class  `Stack`, which pushes an element on top of the stack. If the stack reaches its maximum size, this method throws the exception StackFull.

Apply the most suitable test pattern to determine the test suite that checks the correct behavior of this method.

### Behavior

- Pushes an element on top of the stack
- If the stack is full, throws `StackFull` exception

## Test Pattern

State-Based Testing

## States

- Empty stack
- Partially filled stack
- Full stack

## Baseline

Stack capacity = 3
Stack = [ ]

## Test cases

| TC | Initial Stack | element | Expected                                    |
| -- | ------------- | ------- | ------------------------------------------- |
| 1  | []            | A       | Push successful → [A]                      |
| 2  | [A]           | B       | Push successful → [A, B]                   |
| 3  | [A, B]        | C       | Push successful → [A, B, C] (reaches full) |
| 4  | [A, B, C]     | D       | Exception (StackFull)                       |
