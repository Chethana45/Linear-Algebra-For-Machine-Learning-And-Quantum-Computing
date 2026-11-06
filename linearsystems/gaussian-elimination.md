# Gaussian Elimination

## 1. Introduction

Gaussian Elimination is a direct numerical method used to solve systems of linear equations. It transforms a system into an upper triangular matrix using elementary row operations.

After obtaining the upper triangular form, the unknown variables are calculated using back substitution.

It is one of the fundamental techniques in Linear Algebra and numerical computation.

## 2. Mathematical Representation

A system of linear equations can be represented as:

Ax = b

Where:
- A is the coefficient matrix.
- x is the vector of unknown variables.
- b is the constant vector.

## 3. Elementary Row Operations

Gaussian Elimination uses three elementary row operations:

1. Row Interchange: Ri ↔ Rj
2. Row Scaling: Ri → kRi
3. Row Replacement: Ri → Ri + kRj

These operations preserve the solution of the original system.

## 4. Augmented Matrix

Consider:

2x + y + z = 7
x + 3y + 2z = 13
3x + 2y + 4z = 19

The augmented matrix is:

[2  1  1 | 7]
[1  3  2 | 13]
[3  2  4 | 19]

## 5. Forward Elimination

The objective is to convert the augmented matrix into upper triangular form.

An upper triangular matrix contains zeros below its main diagonal.

Apply elementary row operations to eliminate the elements below each pivot.

The resulting matrix becomes:

[2  1  1 | 7]
[0  5  3 | 19]
[0  0  11 | 22]

## 6. Back Substitution

Start solving from the last equation.

11z = 22

z = 2

5y + 3z = 19

5y + 6 = 19

y = 13/5

2x + y + z = 7

2x + 13/5 + 2 = 7

x = 12/5

## 7. Python Implementation

```python
import numpy as np

A = np.array([
    [2, 1, 1],
    [1, 3, 2],
    [3, 2, 4]
], dtype=float)

b = np.array([7, 13, 19], dtype=float)

solution = np.linalg.solve(A, b)

print("Solution:", solution)
print("Verification:", A @ solution)
