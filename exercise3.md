# Exercise 3

Consider the method

`transfer(int amount, Account destination)`

from the `Account class` that transfers a certain amount of money from the source account (the invoked object) to the destination account.
This method works correctly when the transferred amount is greater than 0, the source account is in the abstract state active, and the destination account is not in the abstract state inactive.

Perform a domain analysis and design the test cases that verify the correct domain implementation for this method.

Consider also that the state invariants of the class Account are the following:

* abstract state active: balance >= 0 && inactive < 500;
* abstract state overdrawn: balance < 0 && inactive < 500;
* abstract state inactive: inactive >= 500.

What is the impact of the designed tests if you consider an additional
constraint: the amount to transfer cannot be greater than the balance of the source account? Design the test cases considering this extra condition.

### Domain Analysis

- amount > 0
- source account is active
- destination account is NOT inactive

### Baseline (valid case)

amount = 100  
source = active  
destination = active  

## Test cases

| TC | amount | source state | destination state | Expected |
|----|--------|--------------|-------------------|----------|
| 1  | 100    | active       | active            | Success  |
| 2  | 1      | active       | active            | Success (boundary: amount > 0) |
| 3  | -1     | active       | active            | Invalid (amount ≤ 0) |
| 4  | 100    | inactive     | active            | Invalid (source not active) |
| 5  | 100    | overdrawn    | active            | Invalid (source not active) |
| 6  | 100    | active       | inactive          | Invalid (destination inactive) |
| 7  | 100    | active       | overdrawn         | Success |

---

### Additional Constraint

The amount to transfer cannot be greater than the balance of the source account:

- amount ≤ balance


## Additional Test Cases

| TC | amount | balance | source state | destination state | Expected |
|----|--------|---------|--------------|-------------------|----------|
| 8  | 50     | 100     | active       | active            | Success |
| 9  | 100    | 100     | active       | active            | Success (boundary) |
| 10 | 150    | 100     | active       | active            | Invalid (amount > balance) |

---

### Steps of the Test Pattern

1. Identified relevant states of the Account class (active, overdrawn, inactive)  
2. Determined valid and invalid state combinations  
3. Applied constraints on amount  
4. Added additional constraint (amount ≤ balance)  
5. Designed test cases covering all relevant scenarios  