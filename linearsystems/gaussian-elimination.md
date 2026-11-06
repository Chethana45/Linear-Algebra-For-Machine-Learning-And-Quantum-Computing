# Gaussian Elimination

## 1. Introduction

Gaussian Elimination is a direct numerical method used to solve systems of linear equations. It transforms a system into an upper triangular matrix using elementary row operations.

After obtaining the upper triangular form, the unknown variables are calculated using back substitution.

It is one of the fundamental techniques in Linear Algebra and numerical computation.

## 2. Learning Objectives

- Understand systems of linear equations.
- Represent equations using augmented matrices.
- Apply elementary row operations.
- Perform forward elimination.
- Understand pivot elements and partial pivoting.
- Solve equations using back substitution.
- Implement Gaussian Elimination using Python.

## 3. Mathematical Foundation

A system of linear equations can be represented as:

Ax = b

Where:

- A is the coefficient matrix.
- x is the vector of unknown variables.
- b is the constant vector.

For example:

2x + y = 5
x + 3y = 7

The matrix representation is:

A = [[2, 1], [1, 3]]

x = [x, y]

b = [5, 7]

## 4. Elementary Row Operations

Gaussian Elimination uses three elementary row operations:

1. Row Interchange: Ri ↔ Rj
2. Row Scaling: Ri → kRi
3. Row Replacement: Ri → Ri + kRj

These operations preserve the solution of the original system.

## 5. Augmented Matrix

Consider:

2x + y + z = 7
x + 3y + 2z = 13
3x + 2y + 4z = 19

The augmented matrix is:

[2  1  1 | 7]
[1  3  2 | 13]
[3  2  4 | 19]

The objective is to eliminate elements below the main diagonal.

## 6. Forward Elimination

Forward elimination converts the augmented matrix into upper triangular form.

An upper triangular matrix contains zeros below its main diagonal.

For example:

[2  1  1 | 7]
[0  5  3 | 19]
[0  0  11 | 33]

The last equation can now be solved first.

## 7. Back Substitution

Consider the triangular system:

2x + y + z = 7
5y + 3z = 19
11z = 33

Starting from the last equation:

11z = 33

z = 3

Substitute z into the second equation:

5y + 3(3) = 19

5y = 10

y = 2

Substitute y and z into the first equation:

2x + 2 + 3 = 7

2x = 2

x = 1

Final solution:

x = 1, y = 2, z = 3

## 8. Pivot Elements and Partial Pivoting

A pivot is the element used to eliminate other elements in a column.

Partial pivoting selects the element with the largest absolute value in the current column and swaps rows when necessary.

Advantages of partial pivoting:

- Avoids division by zero when possible.
- Reduces numerical instability.
- Improves computational accuracy.

## 9. Python Implementation

The following implementation performs Gaussian Elimination with partial pivoting and back substitution.

```python
import numpy as np

def gaussian_elimination(A, b):
    A = np.array(A, dtype=float)
    b = np.array(b, dtype=float)

    n = len(b)
    augmented = np.column_stack((A, b))

    # Forward elimination
    for i in range(n):
        pivot = i + np.argmax(np.abs(augmented[i:, i]))

        if np.isclose(augmented[pivot, i], 0):
            raise ValueError("Matrix is singular or has no unique solution")

        augmented[[i, pivot]] = augmented[[pivot, i]]

        for j in range(i + 1, n):
            factor = augmented[j, i] / augmented[i, i]
            augmented[j] -= factor * augmented[i]

    # Back substitution
    x = np.zeros(n)

    for i in range(n - 1, -1, -1):
        x[i] = (
            augmented[i, -1]
            - np.dot(augmented[i, i + 1:n], x[i + 1:n])
        ) / augmented[i, i]

    return x


A = [
    [2, 1, 1],
    [1, 3, 2],
    [3, 2, 4]
]

b = [7, 13, 19]

solution = gaussian_elimination(A, b)

print("Solution:", solution)
print("Verification:", np.array(A) @ solution)
