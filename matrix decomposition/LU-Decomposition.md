# LU Decomposition

## 1. Introduction

LU Decomposition, also known as LU Factorization, is a matrix decomposition technique in linear algebra.

It involves expressing a square matrix as the product of two triangular matrices:

- **L – Lower Triangular Matrix**
- **U – Upper Triangular Matrix**

LU Decomposition is commonly used to solve systems of linear equations, calculate determinants, and perform matrix operations efficiently.

## 2. Mathematical Representation

The LU decomposition of a matrix is represented as:

\[
A = LU
\]

Where:

- **A:** Original square matrix.
- **L:** Lower triangular matrix containing zeros above the main diagonal.
- **U:** Upper triangular matrix containing zeros below the main diagonal.

## 3. Understanding L and U Matrices

### Lower Triangular Matrix (L)

A lower triangular matrix is a square matrix in which all elements above the main diagonal are zero.

Example:

\[
L =
\begin{bmatrix}
1 & 0 & 0\\
2 & 1 & 0\\
3 & 4 & 1
\end{bmatrix}
\]

### Upper Triangular Matrix (U)

An upper triangular matrix is a square matrix in which all elements below the main diagonal are zero.

Example:

\[
U =
\begin{bmatrix}
2 & 3 & 1\\
0 & 4 & 5\\
0 & 0 & 6
\end{bmatrix}
\]

## 4. How LU Decomposition Works

LU Decomposition is closely related to Gaussian elimination.

The main steps are:

1. Start with the original matrix A.
2. Apply Gaussian elimination to eliminate elements below the main diagonal.
3. Store the elimination multipliers in the lower triangular matrix L.
4. The resulting upper triangular matrix becomes U.
5. Multiply L and U to reconstruct the original matrix.

## 5. Worked Example

Consider the matrix:

\[
A =
\begin{bmatrix}
2 & 3\\
4 & 7
\end{bmatrix}
\]

We want to decompose it into L and U.

### Step 1: Eliminate the element below the pivot

The first pivot is 2.

Multiplier:

\[
m_{21} = \frac{4}{2} = 2
\]

Perform the row operation:

\[
R_2 \rightarrow R_2 - 2R_1
\]

This gives:

\[
U =
\begin{bmatrix}
2 & 3\\
0 & 1
\end{bmatrix}
\]

### Step 2: Construct the L Matrix

Place the elimination multiplier below the main diagonal and put 1s on the diagonal.

\[
L =
\begin{bmatrix}
1 & 0\\
2 & 1
\end{bmatrix}
\]

### Step 3: Verify the Decomposition

\[
LU =
\begin{bmatrix}
1 & 0\\
2 & 1
\end{bmatrix}
\begin{bmatrix}
2 & 3\\
0 & 1
\end{bmatrix}
\]

\[
=
\begin{bmatrix}
2 & 3\\
4 & 7
\end{bmatrix}
\]

Therefore:

\[
A = LU
\]

The original matrix is successfully reconstructed.

## 6. Python Implementation Using NumPy and SciPy

### Import Libraries

```python
import numpy as np
from scipy.linalg import lu
```

### Create a Matrix

```python
A = np.array([
    [2, 3],
    [4, 7]
])

print("Original Matrix:")
print(A)
```

### Perform LU Decomposition

```python
P, L, U = lu(A)

print("Permutation Matrix (P):")
print(P)

print("Lower Triangular Matrix (L):")
print(L)

print("Upper Triangular Matrix (U):")
print(U)
```

**Note:** SciPy uses the convention:

\[
A = PLU
\]

Here, P is the permutation matrix. For this example, no row swapping is required, so P is the identity matrix.

### Reconstruct the Original Matrix

```python
A_reconstructed = P @ L @ U

print("Reconstructed Matrix:")
print(A_reconstructed)

print("Verification:")
print(np.allclose(A, A_reconstructed))
```

`np.allclose()` checks whether the reconstructed matrix is approximately equal to the original matrix.

## 7. Solving Linear Equations Using LU Decomposition

Consider a system of linear equations:

\[
Ax = b
\]

Using LU decomposition:

\[
LUx = b
\]

We solve this in two steps:

1. Solve \(Ly = b\) using forward substitution.
2. Solve \(Ux = y\) using backward substitution.

### Python Implementation

```python
import numpy as np
from scipy.linalg import lu_factor, lu_solve

A = np.array([
    [2, 3],
    [4, 7]
])

b = np.array([8, 18])

lu_matrix, piv = lu_factor(A)

x = lu_solve((lu_matrix, piv), b)

print("Solution:")
print(x)
```

## 8. Applications of LU Decomposition

### 1. Solving Linear Equations

LU decomposition helps solve systems of linear equations efficiently, especially when multiple right-hand sides use the same coefficient matrix.

### 2. Computing Determinants

The determinant of a matrix can be calculated using its triangular factors, with the permutation sign taken into account when pivoting is used.

### 3. Matrix Inversion

LU decomposition can be used to calculate the inverse of a matrix by solving multiple linear systems.

### 4. Numerical Computing

It is widely used in scientific computing, engineering simulations, and numerical analysis.

### 5. Machine Learning

LU factorization can support numerical operations involving linear systems and matrix calculations in machine learning algorithms.

## 9. Advantages and Limitations

### Advantages

- Efficient for solving multiple linear systems with the same matrix.
- Simplifies matrix calculations.
- Useful for determinant calculations.
- Based on Gaussian elimination.

### Limitations

- Basic LU decomposition may fail when a pivot element is zero.
- Pivoting may be required for numerical stability.
- Standard LU decomposition is primarily used for square matrices.

## 10. LU Decomposition vs SVD

| Feature | LU Decomposition | SVD |
|---|---|---|
| Decomposition | A = LU | A = UΣVᵀ |
| Matrix type | Primarily square matrices | Square and rectangular matrices |
| Main purpose | Solving linear systems | Matrix analysis and approximation |
| Components | Lower and upper triangular matrices | Singular vectors and singular values |
| Applications | Linear equations, determinants | PCA, compression, dimensionality reduction |

## 11. Conclusion

LU Decomposition is an important matrix factorization technique that simplifies complex matrix operations by splitting a matrix into lower and upper triangular matrices.

It is particularly useful for solving systems of linear equations, computing determinants, and performing numerical computations efficiently.

Understanding LU Decomposition provides a strong foundation for advanced topics in numerical linear algebra and machine learning.

## References

- [SciPy – LU Factorization](https://docs.scipy.org/doc/scipy/reference/generated/scipy.linalg.lu.html)
- [NumPy Documentation](https://numpy.org/doc/stable/)
- [Gaussian Elimination](https://en.wikipedia.org/wiki/Gaussian_elimination)

---

*Part of my Linear Algebra for Machine Learning and Quantum Computing learning repository.*
