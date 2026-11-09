# Matrix Inverse and Determinant

## 1. Introduction

Matrix inverse and determinant are important concepts in linear algebra.

- **Matrix Inverse:** The inverse of a square matrix is a matrix that produces the identity matrix when multiplied by the original matrix.
- **Determinant:** The determinant is a scalar value calculated from a square matrix. It helps determine whether a matrix is invertible.

These concepts are widely used in solving linear equations, machine learning, numerical computing, and transformations.

## 2. Matrix Determinant

The determinant is a single numerical value associated with a square matrix.

It is represented as:

\[
\det(A) \quad \text{or} \quad |A|
\]

### Determinant of a 2 × 2 Matrix

For a matrix:

\[
A =
\begin{bmatrix}
a & b\\
c & d
\end{bmatrix}
\]

The determinant is:

\[
\det(A) = ad-bc
\]

### Worked Example

Consider:

\[
A =
\begin{bmatrix}
2 & 3\\
4 & 5
\end{bmatrix}
\]

\[
\det(A) = (2 \times 5)-(3 \times 4)
\]

\[
=10-12
\]

\[
\boxed{\det(A)=-2}
\]

### Determinant of a 3 × 3 Matrix

For:

\[
A =
\begin{bmatrix}
a & b & c\\
d & e & f\\
g & h & i
\end{bmatrix}
\]

The determinant is:

\[
\det(A)=a(ei-fh)-b(di-fg)+c(dh-eg)
\]

## 3. Properties of Determinants

1. The determinant is defined only for square matrices.
2. If the determinant is zero, the matrix is singular.
3. If the determinant is non-zero, the matrix is invertible.
4. The determinant of an identity matrix is 1.
5. The determinant of a transpose equals the determinant of the original matrix.

\[
\det(A^T)=\det(A)
\]

6. The determinant of a product is the product of the determinants.

\[
\det(AB)=\det(A)\det(B)
\]

## 4. Matrix Inverse

The inverse of a square matrix A is represented by:

\[
A^{-1}
\]

It satisfies:

\[
AA^{-1}=A^{-1}A=I
\]

Where I is the identity matrix.

A matrix has an inverse only if its determinant is non-zero.

### Inverse of a 2 × 2 Matrix

For:

\[
A =
\begin{bmatrix}
a & b\\
c & d
\end{bmatrix}
\]

Its inverse is:

\[
A^{-1} =
\frac{1}{ad-bc}
\begin{bmatrix}
d & -b\\
-c & a
\end{bmatrix}
\]

Condition:

\[
ad-bc \neq 0
\]

## 5. Worked Example

Consider:

\[
A =
\begin{bmatrix}
2 & 1\\
5 & 3
\end{bmatrix}
\]

### Step 1: Calculate the Determinant

\[
\det(A)=(2 \times 3)-(1 \times 5)
\]

\[
=6-5=1
\]

Since the determinant is non-zero, the inverse exists.

### Step 2: Calculate the Inverse

Using the formula:

\[
A^{-1} =
\frac{1}{1}
\begin{bmatrix}
3 & -1\\
-5 & 2
\end{bmatrix}
\]

Therefore:

\[
\boxed{
A^{-1} =
\begin{bmatrix}
3 & -1\\
-5 & 2
\end{bmatrix}
}
\]

### Step 3: Verify the Inverse

\[
AA^{-1} =
\begin{bmatrix}
2 & 1\\
5 & 3
\end{bmatrix}
\begin{bmatrix}
3 & -1\\
-5 & 2
\end{bmatrix}
\]

\[
=
\begin{bmatrix}
1 & 0\\
0 & 1
\end{bmatrix}
\]

The result is the identity matrix, so the inverse is correct.

## 6. Python Implementation Using NumPy

### Import Library

```python
import numpy as np
```

### Create a Matrix

```python
A = np.array([
    [2, 1],
    [5, 3]
])

print("Original Matrix:")
print(A)
```

### Calculate Determinant

```python
det = np.linalg.det(A)

print("Determinant:")
print(det)
```

### Calculate Matrix Inverse

```python
if not np.isclose(det, 0):
    inverse = np.linalg.inv(A)
    print("Inverse Matrix:")
    print(inverse)
else:
    print("Matrix is not invertible")
```

### Verify the Inverse

```python
result = A @ inverse

print("A multiplied by its inverse:")
print(result)

print("Verification:")
print(np.allclose(result, np.eye(A.shape[0])))
```

## 7. Singular and Non-Singular Matrices

### Singular Matrix

A square matrix is singular when its determinant is zero.

\[
\det(A)=0
\]

It does not have an inverse.

Example:

\[
A =
\begin{bmatrix}
1 & 2\\
2 & 4
\end{bmatrix}
\]

\[
\det(A)=(1 \times 4)-(2 \times 2)=0
\]

Therefore, the matrix is singular.

### Non-Singular Matrix

A square matrix is non-singular when its determinant is non-zero.

\[
\det(A)\neq 0
\]

It has an inverse.

## 8. Applications

### 1. Solving Linear Equations

Matrix inverse can be used to solve a system of linear equations.

\[
Ax=b
\]

If A is invertible:

\[
x=A^{-1}b
\]

### 2. Machine Learning

Matrix operations are used in linear regression and other mathematical computations.

### 3. Computer Graphics

Matrix inverses help reverse geometric transformations.

### 4. Numerical Computing

Determinants and inverses are useful in mathematical and scientific computations.

### 5. Quantum Computing

Invertible matrices and unitary transformations are important in representing quantum operations.

## 9. Difference Between Matrix Inverse and Determinant

| Feature | Matrix Inverse | Determinant |
|---|---|---|
| Result | Matrix | Scalar |
| Notation | A⁻¹ | det(A) |
| Purpose | Finds inverse transformation | Checks invertibility |
| Requirement | Square matrix with non-zero determinant | Square matrix |
| Output | Same dimensions as A | Single numerical value |

## 10. Conclusion

Matrix inverse and determinant are fundamental concepts in linear algebra.

The determinant determines whether a square matrix is invertible, while the inverse helps solve systems of linear equations and perform reverse transformations.

These concepts provide an important mathematical foundation for machine learning, numerical computing, and quantum computing.

## References

- [NumPy – Matrix Inverse](https://numpy.org/doc/stable/reference/generated/numpy.linalg.inv.html)
- [NumPy – Determinant](https://numpy.org/doc/stable/reference/generated/numpy.linalg.det.html)
- [NumPy Documentation](https://numpy.org/doc/stable/)

---

*Part of my Linear Algebra for Machine Learning and Quantum Computing learning repository.*
