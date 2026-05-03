# Test Patterns Cheat Sheet

## Overview

Test patterns are strategies used to design effective test cases based on the characteristics of the system under test.

---

## 1. Input Domain Partitioning (Equivalence Classes)

Split input values into groups (valid / invalid) and test one representative from each group.

### Use when:
- Input constraints exist
- Large input space

### Example:
x > 0  
Valid: {1, 2, 3}  
Invalid: {0, -1}

---

## 2. Boundary Value Analysis (BVA)

Test values at and around the limits of the domain.

### Use when:
- Conditions use <, ≤, >, ≥

### Example:
x ≤ 10 → test:
- 9 (below)
- 10 (boundary)
- 11 (above)

👉 Most important pattern

---

## 3. Decision Table Testing

Test combinations of conditions and their outcomes.

### Use when:
- Multiple rules / business logic
- Complex condition combinations

---

## 4. Cause-Effect Graphing

Model logical relationships between inputs and outputs.

### Use when:
- Complex logical dependencies
- Many interacting conditions

---

## 5. State-Based Testing

Test behavior depending on system state and transitions.

### Use when:
- Objects have states
- Behavior changes over time

### Example states:
- Empty
- Partially full
- Full

---

## 6. Output-Based Partitioning (Behavior-Based)

Group tests based on different outputs of the method.

### Use when:
- Output varies significantly

### Example:
- Empty result
- Single value
- Multiple values

---

## 7. Path Testing (Control Flow Testing)

Test different execution paths in the code.

### Use when:
- Multiple branches (if/else, loops)

---

## 8. Error / Exception Testing

Focus on invalid inputs and expected exceptions.

### Use when:
- Method throws exceptions

---

## 9. Combinatorial Testing

Test combinations of input parameters.

### Use when:
- Multiple interacting inputs

---

## 10. Recursive Testing Pattern

Test recursive functions.

### Always test:
- Base case
- Recursive case
- Edge case

---

# Patterns Used in Exercises

| Exercise | Pattern |
|----------|--------|
| 1–2 | Domain + Boundary |
| 3 | State-Based |
| 4–6 | Domain + Boundary (with dependencies) |
| 7 | Domain + Output-Based |
| 8 | State-Based |

---

# Quick Selection Guide

Use this to choose the right pattern:

- Constraints → Domain + Boundary  
- Object states → State-Based  
- Business rules → Decision Table  
- Output variation → Output-Based  

---

# Key Takeaway

Choose the pattern that best fits the problem.

You do not need all patterns — just the right one.