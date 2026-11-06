
# Matrix Inverse Method

## 1. Introduction

The **Matrix Inverse Method** is a direct method used to solve a system of linear equations by calculating the inverse of its coefficient matrix.

A system of linear equations can be represented as:

\[
AX=B
\]

Where:

- \(A\) = Coefficient matrix.
- \(X\) = Unknown variable matrix.
- \(B\) = Constant matrix.

If the inverse of matrix \(A\) exists, we can multiply both sides by \(A^{-1}\).

\[
A^{-1}AX=A^{-1}B
\]

Since:

\[
A^{-1}A=I
\]

We get:

\[
IX=A^{-1}B
\]

Therefore:

\[
\boxed{X=A^{-1}B}
\]

This is the matrix inverse method.

---

## 2. Learning Objectives

After studying this topic, you should be able to:

- Understand the concept of an inverse matrix.
- Represent linear equations in matrix form.
- Calculate the inverse of a matrix.
- Solve systems of linear equations using the inverse.
- Understand when an inverse exists.
- Implement the method using Python.
- Identify its advantages and limitations.

---

## 3. What Is an Inverse Matrix?

The inverse of a square matrix \(A\) is another matrix \(A^{-1}\) such that:

\[
\boxed{AA^{-1}=A^{-1}A=I}
\]

Where:

- \(A\) = Original matrix.
- \(A^{-1}\) = Inverse matrix.
- \(I\) = Identity matrix.

### Example

Consider:

\[
A=
\begin{bmatrix}
2&1\\
1&3
\end{bmatrix}
\]

Its inverse is:

\[
A^{-1}=
\frac{1}{5}
\begin{bmatrix}
3&-1\\
-1&2
\end{bmatrix}
\]

Multiplying the original matrix by its inverse:

\[
AA^{-1}
=
\begin{bmatrix}
2&1\\
1&3
\end{bmatrix}
\frac{1}{5}
\begin{bmatrix}
3&-1\\
-1&2
\end{bmatrix}
\]

\[
=
\frac{1}{5}
\begin{bmatrix}
6-1&-2+2\\
3-3&-1+6
\end{bmatrix}
\]

\[
=
\frac{1}{5}
\begin{bmatrix}
5&0\\
0&5
\end{bmatrix}
\]

\[
=
\begin{bmatrix}
1&0\\
0&1
\end{bmatrix}
=I
\]

Therefore, the calculated matrix is the inverse of \(A\).

---

## 4. Condition for the Existence of an Inverse

A matrix has an inverse only if:

1. It is a square matrix.
2. Its determinant is non-zero.

Mathematically:

\[
\boxed{\det(A)\neq 0}
\]

If:

\[
\det(A)=0
\]

The matrix is called a **singular matrix**, and its inverse does not exist.

If:

\[
\det(A)\neq 0
\]

The matrix is called a **non-singular matrix**, and its inverse exists.

### Example

Consider:

\[
A=
\begin{bmatrix}
2&4\\
1&2
\end{bmatrix}
\]

Its determinant is:

\[
\det(A)=(2)(2)-(4)(1)
\]

\[
=4-4=0
\]

Therefore, the matrix is singular, and its inverse does not exist.

---

## 5. Methods to Calculate the Inverse of a Matrix

There are different methods for calculating the inverse of a matrix.

### Method 1: Adjoint Method

For a square matrix:

\[
\boxed{A^{-1}=\frac{\operatorname{adj}(A)}{\det(A)}}
\]

Where:

- \(\operatorname{adj}(A)\) = Adjoint of matrix \(A\).
- \(\det(A)\) = Determinant of matrix \(A\).

This formula is applicable only when the determinant is non-zero.

### Method 2: Gauss-Jordan Elimination

In this method, the original matrix is augmented with the identity matrix.

\[
[A|I]
\]

Using elementary row operations, transform the left side into an identity matrix.

\[
[A|I]\longrightarrow[I|A^{-1}]
\]

The right side becomes the inverse matrix.

### Example

Consider:

\[
A=
\begin{bmatrix}
2&1\\
1&3
\end{bmatrix}
\]

Form the augmented matrix:

\[
\left[
\begin{array}{cc|cc}
2&1&1&0\\
1&3&0&1
\end{array}
\right]
\]

After applying elementary row operations and reducing the left side to the identity matrix:

\[
\left[
\begin{array}{cc|cc}
1&0&3/5&-1/5\\
0&1&-1/5&2/5
\end{array}
\right]
\]

Therefore:

\[
\boxed{
A^{-1}=
\begin{bmatrix}
3/5&-1/5\\
-1/5&2/5
\end{bmatrix}
}
\]

---

## 6. Solving Linear Equations Using the Matrix Inverse Method

Consider the following system:

\[
\begin{aligned}
2x+y&=5\\
x+3y&=7
\end{aligned}
\]

### Step 1: Convert into matrix form

The system can be written as:

\[
AX=B
\]

Where:

\[
A=
\begin{bmatrix}
2&1\\
1&3
\end{bmatrix}
\]

\[
X=
\begin{bmatrix}
x\\
y
\end{bmatrix}
\]

\[
B=
\begin{bmatrix}
5\\
7
\end{bmatrix}
\]

Therefore:

\[
\begin{bmatrix}
2&1\\
1&3
\end{bmatrix}
\begin{bmatrix}
x\\
y
\end{bmatrix}
=
\begin{bmatrix}
5\\
7
\end{bmatrix}
\]

### Step 2: Calculate the determinant

For a 2 × 2 matrix:

\[
A=
\begin{bmatrix}
a&b\\
c&d
\end{bmatrix}
\]

The determinant is:

\[
\det(A)=ad-bc
\]

For our matrix:

\[
\det(A)=(2)(3)-(1)(1)
\]

\[
=6-1=5
\]

Since:

\[
\det(A)\neq 0
\]

The inverse exists.

### Step 3: Calculate the inverse

For a 2 × 2 matrix:

\[
A^{-1}=
\frac{1}{ad-bc}
\begin{bmatrix}
d&-b\\
-c&a
\end{bmatrix}
\]

Substituting the values:

\[
A^{-1}=
\frac{1}{5}
\begin{bmatrix}
3&-1\\
-1&2
\end{bmatrix}
\]

### Step 4: Apply the inverse formula

We know:

\[
X=A^{-1}B
\]

Substitute:

\[
\begin{bmatrix}
x\\
y
\end{bmatrix}
=
\frac{1}{5}
\begin{bmatrix}
3&-1\\
-1&2
\end{bmatrix}
\begin{bmatrix}
5\\
7
\end{bmatrix}
\]

Multiply the matrices:

\[
=
\frac{1}{5}
\begin{bmatrix}
(3)(5)+(-1)(7)\\
(-1)(5)+(2)(7)
\end{bmatrix}
\]

\[
=
\frac{1}{5}
\begin{bmatrix}
8\\
9
\end{bmatrix}
\]

Therefore:

\[
\boxed{x=\frac{8}{5}=1.6}
\]

\[
\boxed{y=\frac{9}{5}=1.8}
\]

### Final Answer

\[
\boxed{x=1.6,\quad y=1.8}
\]

---

## 7. Python Implementation Using NumPy

Python provides the NumPy library to calculate matrix inverses.

### Code

```python
import numpy as np

# Coefficient matrix
A = np.array([
    [2, 1],
    [1, 3]
], dtype=float)

# Constant matrix
B = np.array([5, 7], dtype=float)

# Check whether the inverse exists
det = np.linalg.det(A)

if not np.isclose(det, 0):
    # Calculate inverse
    A_inverse = np.linalg.inv(A)

    print("Inverse Matrix:")
    print(A_inverse)

    # Calculate solution
    X = A_inverse @ B

    print("Solution:")
    print(X)

    # Verify the solution
    print("Verification:")
    print(A @ X)
else:
    print("Inverse does not exist")
```

### Output

```text
Inverse Matrix:
[[ 0.6 -0.2]
 [-0.2  0.4]]

Solution:
[1.6 1.8]

Verification:
[5. 7.]
```

The result is:

\[
x=1.6,\quad y=1.8
\]

The verification produces the original constant vector:

\[
AX=B
\]

---

## 8. Important NumPy Functions

| Function | Purpose |
|---|---|
| `np.linalg.det(A)` | Calculates determinant |
| `np.linalg.inv(A)` | Calculates inverse |
| `np.eye(n)` | Creates identity matrix |
| `np.linalg.matrix_rank(A)` | Calculates matrix rank |
| `np.linalg.solve(A, B)` | Directly solves a linear system |
| `A @ B` | Performs matrix multiplication |

### Important Practical Note

Although the inverse method is useful for understanding linear algebra, explicitly calculating the inverse is generally not the best way to solve a system computationally.

Instead of:

```python
X = np.linalg.inv(A) @ B
```

Prefer:

```python
X = np.linalg.solve(A, B)
```

`np.linalg.solve()` directly solves the system and is generally more efficient and numerically stable.

---

## 9. Properties of an Inverse Matrix

### Property 1: Identity

\[
AA^{-1}=I
\]

### Property 2: Inverse of an inverse

\[
(A^{-1})^{-1}=A
\]

### Property 3: Transpose of an inverse

\[
(A^{-1})^T=(A^T)^{-1}
\]

### Property 4: Inverse of a product

\[
(AB)^{-1}=B^{-1}A^{-1}
\]

### Property 5: Inverse of an identity matrix

\[
I^{-1}=I
\]

### Property 6: Determinant of an inverse

\[
\det(A^{-1})=\frac{1}{\det(A)}
\]

These properties are useful when simplifying matrix expressions.

---

## 10. Advantages

1. Provides a direct mathematical approach to solving linear systems.
2. Easy to understand and derive.
3. Gives an exact solution in theory when calculations are exact and the inverse exists.
4. Useful for studying matrix algebra.
5. Helps understand the relationship between determinants, inverses, and linear equations.

## 11. Disadvantages

1. The coefficient matrix must be square.
2. The determinant must be non-zero.
3. Calculating the inverse can be computationally expensive for large matrices.
4. Numerical errors may occur due to floating-point calculations.
5. Not suitable for singular matrices.
6. Directly calculating the inverse is usually less efficient than solving the system using numerical solvers.

---

## 12. Applications

### Computer Graphics

Matrix inverses are used in coordinate transformations, rotations, and scaling operations.

### Robotics

Used in coordinate transformations and solving mathematical relationships between robot components.

### Machine Learning

Matrix algebra is used in linear regression, optimization, and numerical computation.

### Engineering

Used to solve systems of equations in electrical, mechanical, and structural engineering.

### Scientific Computing

Used in numerical analysis and mathematical modeling.

---

## 13. Comparison with Other Methods

| Method | Type | Main Idea |
|---|---|---|
| Gaussian Elimination | Direct | Converts the matrix into upper triangular form |
| Gauss-Jordan Elimination | Direct | Converts the matrix into reduced row-echelon form |
| LU Decomposition | Direct | Factorizes a matrix into lower and upper triangular matrices |
| Cramer's Rule | Direct | Uses determinants to calculate individual variables |
| Jacobi Method | Iterative | Uses previous iteration values |
| Gauss-Seidel Method | Iterative | Uses newly updated values |
| Matrix Inverse Method | Direct | Calculates the inverse and multiplies it by the constant vector |

---

## 14. Practice Problems

### Problem 1

Solve using the matrix inverse method:

\[
\begin{aligned}
2x+y&=7\\
x+2y&=8
\end{aligned}
\]

Expected answer:

\[
x=2,\quad y=3
\]

### Problem 2

Find the inverse of:

\[
A=
\begin{bmatrix}
4&2\\
1&3
\end{bmatrix}
\]

### Problem 3

Check whether the following matrix has an inverse:

\[
A=
\begin{bmatrix}
2&4\\
1&2
\end{bmatrix}
\]

### Problem 4

Explain the difference between singular and non-singular matrices.

### Problem 5

Write a Python program to solve a system of linear equations using NumPy's matrix inverse function.

---

## 15. Conclusion

The Matrix Inverse Method is a direct technique for solving systems of linear equations.

It uses the relationship:

\[
\boxed{X=A^{-1}B}
\]

The method works only when the coefficient matrix is square and has a non-zero determinant.

It is an important concept in linear algebra and is widely used in engineering, computer graphics, robotics, and scientific computing.

Although it is useful for understanding matrix operations, practical numerical programs generally prefer direct solvers such as `np.linalg.solve()` instead of explicitly calculating the inverse.

---

## 16. References

- Linear Algebra textbooks.
- NumPy Documentation: https://numpy.org/doc/
- NumPy Linear Algebra: https://numpy.org/doc/stable/reference/routines.linalg.html
- Numerical Methods lecture notes.
