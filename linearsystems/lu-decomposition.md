
# Gauss-Jordan Elimination

## 1. Introduction

Gauss-Jordan Elimination is a direct method used to solve systems of linear equations by transforming an augmented matrix into Reduced Row Echelon Form (RREF).

Unlike Gaussian Elimination, which requires back substitution, Gauss-Jordan Elimination eliminates elements both above and below each pivot.

The final matrix directly provides the values of the unknown variables.

## 2. Learning Objectives

- Understand Reduced Row Echelon Form.
- Apply elementary row operations.
- Transform matrices into RREF.
- Solve systems of linear equations.
- Identify unique, infinite and inconsistent solutions.
- Calculate matrix inverses.
- Implement the algorithm using Python.

## 3. Mathematical Foundation

Consider a system of linear equations:

\[
Ax=b
\]

Where:

- A is the coefficient matrix.
- x is the unknown variable vector.
- b is the constant vector.

The augmented matrix is represented as:

\[
[A|b]
\]

The objective is to transform the augmented matrix into:

\[
[I|x]
\]

Where I is the identity matrix.

This is possible when the coefficient matrix is invertible.

## 4. Reduced Row Echelon Form (RREF)

A matrix is in Reduced Row Echelon Form if it satisfies the following conditions:

1. All rows containing only zeros appear at the bottom.
2. The first non-zero element in every non-zero row is 1.
3. Each leading 1 is the only non-zero element in its column.
4. The leading 1 in each successive row appears to the right of the leading 1 in the previous row.

Example:

\[
\begin{bmatrix}
1&0&0\\
0&1&0\\
0&0&1
\end{bmatrix}
\]

This is an identity matrix and is in RREF.

## 5. Elementary Row Operations

Gauss-Jordan Elimination uses three elementary row operations:

1. Row interchange:

\[
R_i \leftrightarrow R_j
\]

2. Row scaling:

\[
R_i \rightarrow kR_i
\]

3. Row replacement:

\[
R_i \rightarrow R_i+kR_j
\]

These operations preserve the solution of the system.

## 6. Numerical Example

Consider the system:

\[
\begin{aligned}
x+y+z&=6\\
2x+y-z&=1\\
x-y+2z&=5
\end{aligned}
\]

The augmented matrix is:

\[
\begin{bmatrix}
1&1&1&|&6\\
2&1&-1&|&1\\
1&-1&2&|&5
\end{bmatrix}
\]

### Step 1: Eliminate elements below the first pivot.

Apply:

\[
R_2\rightarrow R_2-2R_1
\]

\[
R_3\rightarrow R_3-R_1
\]

The matrix becomes:

\[
\begin{bmatrix}
1&1&1&|&6\\
0&-1&-3&|&-11\\
0&-2&1&|&-1
\end{bmatrix}
\]

### Step 2: Eliminate the element below the second pivot.

Apply:

\[
R_3\rightarrow R_3-2R_2
\]

The matrix becomes:

\[
\begin{bmatrix}
1&1&1&|&6\\
0&-1&-3&|&-11\\
0&0&7&|&21
\end{bmatrix}
\]

### Step 3: Normalize the third pivot.

Apply:

\[
R_3\rightarrow \frac{R_3}{7}
\]

The matrix becomes:

\[
\begin{bmatrix}
1&1&1&|&6\\
0&-1&-3&|&-11\\
0&0&1&|&3
\end{bmatrix}
\]

### Step 4: Eliminate elements above the third pivot.

Apply:

\[
R_2\rightarrow R_2+3R_3
\]

\[
R_1\rightarrow R_1-R_3
\]

The matrix becomes:

\[
\begin{bmatrix}
1&1&0&|&3\\
0&-1&0&|&-2\\
0&0&1&|&3
\end{bmatrix}
\]

### Step 5: Normalize the second pivot.

Apply:

\[
R_2\rightarrow -R_2
\]

The matrix becomes:

\[
\begin{bmatrix}
1&1&0&|&3\\
0&1&0&|&2\\
0&0&1&|&3
\end{bmatrix}
\]

### Step 6: Eliminate the element above the second pivot.

Apply:

\[
R_1\rightarrow R_1-R_2
\]

Final RREF:

\[
\begin{bmatrix}
1&0&0&|&1\\
0&1&0&|&2\\
0&0&1&|&3
\end{bmatrix}
\]

Therefore:

\[
\boxed{x=1,\quad y=2,\quad z=3}
\]

## 7. Python Implementation

The following implementation uses SymPy to calculate the Reduced Row Echelon Form.

```python
import sympy as sp

A = sp.Matrix([
    [1, 1, 1],
    [2, 1, -1],
    [1, -1, 2]
])

b = sp.Matrix([6, 1, 5])

augmented = A.row_join(b)

rref_matrix, pivots = augmented.rref()

print("Reduced Row Echelon Form:")
sp.pprint(rref_matrix)

print("\nSolution:")
sp.pprint(rref_matrix[:, -1])
```

Expected output:

```text
Matrix([
[1, 0, 0, 1],
[0, 1, 0, 2],
[0, 0, 1, 3]
])

Solution:
Matrix([
[1],
[2],
[3]
])
```

## 8. Types of Solutions

### 8.1 Unique Solution

A system has exactly one solution when every variable has a pivot and there are no contradictory equations.

### 8.2 Infinite Solutions

A system has infinitely many solutions when it is consistent and at least one variable is free.

Example:

\[
x+y=5
\]

This equation has infinitely many solutions because different values of x and y can satisfy it.

### 8.3 No Solution

A system has no solution when it produces a contradictory equation.

Example:

\[
0x+0y=5
\]

This is impossible, so the system is inconsistent.

## 9. Matrix Inverse Using Gauss-Jordan Elimination

Gauss-Jordan Elimination can also be used to calculate the inverse of a square matrix.

Start with the augmented matrix:

\[
[A|I]
\]

Apply elementary row operations until:

\[
[A|I]\rightarrow[I|A^{-1}]
\]

The right-hand side becomes the inverse matrix.

This method works only when A is invertible.

## 10. Applications

- Solving systems of linear equations.
- Calculating matrix inverses.
- Computer graphics.
- Engineering calculations.
- Machine Learning.
- Mathematical modelling.
- Numerical computation.

## 11. Advantages

- Directly produces the solution.
- Does not require back substitution.
- Helps identify inconsistent systems.
- Can calculate matrix inverses.
- Provides a systematic matrix-solving approach.

## 12. Limitations

- Requires many row operations.
- Can be computationally expensive for large matrices.
- Numerical rounding errors may occur.
- Special handling is required for singular matrices.

## 13. Gaussian vs. Gauss-Jordan Elimination

| Feature | Gaussian Elimination | Gauss-Jordan Elimination |
|---|---|---|
| Final form | Row echelon form | Reduced row echelon form |
| Elimination | Below pivots | Above and below pivots |
| Back substitution | Required | Not required |
| Matrix inverse | Possible with additional operations | Directly possible |
| Computation | Generally fewer operations | Generally more operations |

## 14. Practice Questions

1. Convert a matrix into RREF.
2. Solve a 3×3 system using Gauss-Jordan Elimination.
3. Differentiate Gaussian and Gauss-Jordan Elimination.
4. Identify a system with infinitely many solutions.
5. Explain inconsistent systems.
6. Find the inverse of a matrix using row operations.
7. What are the conditions for RREF?

## 15. Conclusion

Gauss-Jordan Elimination is an important matrix-solving technique that provides a systematic way to solve linear systems and calculate matrix inverses.

It is especially useful for understanding matrix transformations, linear independence, and the structure of solutions in Linear Algebra.

## References

- Gilbert Strang - Introduction to Linear Algebra.
- [SymPy Documentation](https://docs.sympy.org/)
- [NumPy Documentation](https://numpy.org/doc/)
