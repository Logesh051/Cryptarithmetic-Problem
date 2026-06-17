# Experiment No. 8: Solve Cryptarithmetic Problem as a CSP (Constraint Satisfaction Problem) using Python

## Name: LOGESH.N.A

## Register Number: 212223240078

## AIM

To solve a Cryptarithmetic Problem as a Constraint Satisfaction Problem (CSP) using Python.

---

## THEORY

Cryptarithmetic is a type of Constraint Satisfaction Problem (CSP) in which digits are represented by letters.

The objective is to assign unique digits (0–9) to letters such that the arithmetic equation is satisfied.

Example:

```text
 SEND
+MORE
-----
MONEY
```

Each letter represents a unique digit and no two letters can have the same value.

---

## ALGORITHM

1. Identify all unique letters in the given words.
2. Generate possible digit assignments.
3. Ensure no two letters have the same digit.
4. Avoid leading zeros.
5. Convert words into numerical values.
6. Check whether the arithmetic equation is satisfied.
7. If satisfied, display the solution.
8. Otherwise continue searching.

---

## PROCEDURE

1. Import the permutations module.
2. Generate possible digit combinations.
3. Assign digits to letters.
4. Check for leading zero constraints.
5. Convert SEND, MORE and MONEY into numbers.
6. Verify whether SEND + MORE = MONEY.
7. Display the solution if found.

---

## PROGRAM

```python
from itertools import permutations

def solve_cryptarithmetic():

    for perm in permutations(range(10), 8):

        S, E, N, D, M, O, R, Y = perm

        if S == 0 or M == 0:
            continue

        SEND = 1000*S + 100*E + 10*N + D
        MORE = 1000*M + 100*O + 10*R + E
        MONEY = 10000*M + 1000*O + 100*N + 10*E + Y

        if SEND + MORE == MONEY:
            return SEND, MORE, MONEY

    return None

solution = solve_cryptarithmetic()

if solution:

    SEND, MORE, MONEY = solution

    print("SEND =", SEND)
    print("MORE =", MORE)
    print("MONEY =", MONEY)

else:
    print("No solution found")
```

---

## SAMPLE INPUT

```text
SEND
MORE
```

---

## SAMPLE OUTPUT

```text
SEND = 9567
MORE = 1085
MONEY = 10652
```

---

## RESULT

Thus a Cryptarithmetic Problem was solved successfully using Python.
