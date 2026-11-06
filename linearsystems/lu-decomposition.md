
# LU Decomposition

## 1. Introduction

LU Decomposition (Lower-Upper Decomposition) is a matrix factorization technique used to express a square matrix as the product of a lower triangular matrix and an upper triangular matrix.

It is widely used in Linear Algebra, numerical analysis, scientific computing, and Machine Learning.

LU Decomposition is particularly useful when solving multiple systems of linear equations with the same coefficient matrix but different constant vectors.

## 2. Learning Objectives

- Understand matrix factorization.
- Identify lower and upper triangular matrices.
- Understand the mathematical foundation of LU Decomposition.
- Learn Doolittle's and Crout's methods.
- Perform LU Decomposition step by step.
- Solve linear equations using forward and backward substitution.
- Implement LU Decomposition using Python.
- Understand its applications in Machine Learning.

## 3. Mathematical Foundation

A square matrix A can be factorized as:

\[
A=LU
\]

Where:

- A is the original square matrix.
- L is a lower triangular matrix.
- U is an upper triangular matrix.

For some matrices, row permutations are required, giving:

\[
PA=LU
\]

where P is a permutation matrix.

### 3.1 Lower Triangular Matrix

A lower triangular matrix contains zeros above its main diagonal.

Example:

\[
L=
\begin{bmatrix}
1&0&0\\
2&1&0\\
3&4&1
\end{bmatrix}
\]

### 3.2 Upper Triangular Matrix

An upper triangular matrix contains zeros below its main diagonal.

Example:

\[
U=
\begin{bmatrix}
2&3&1\\
0&5&2\\
0&0&6
\end{bmatrix}
\]

## 4. Methods of LU Decomposition

There are two commonly used methods.

### 4.1 Doolittle's Method

In Doolittle's method, all diagonal elements of the lower triangular matrix L are equal to 1.

\[
L=
\begin{bmatrix}
1&0&0\\
l_{21}&1&0\\
l_{31}&l_{32}&1
\end{bmatrix}
\]

The upper triangular matrix U contains the remaining calculated coefficients.

### 4.2 Crout's Method

In Crout's method, all diagonal elements of the upper triangular matrix U are equal to 1.

\[
U=
\begin{bmatrix}
1&u_{12}&u_{13}\\
0&1&u_{23}\\
0&0&1
\end{bmatrix}
\]

Both methods aim to factorize the original matrix into triangular matrices.

## 5. Numerical Example

Consider the matrix:

\[
A=
\begin{bmatrix}
2&1&1\\
4&-6&0\\
-2&7&2
\end{bmatrix}
\]

We need to find matrices L and U such that:

\[
A=LU
\]

### Step 1: Assume the Structure of L and U

Using Doolittle's method:

\[
L=
\begin{bmatrix}
1&0&0\\
l_{21}&1&0\\
l_{31}&l_{32}&1
\end{bmatrix}
\]

\[
U=
\begin{bmatrix}
u_{11}&u_{12}&u_{13}\\
0&u_{22}&u_{23}\\
0&0&u_{33}
\end{bmatrix}
\]

### Step 2: Calculate the First Row of U

From the first row of A:

\[
u_{11}=2
\]

\[
u_{12}=1
\]

\[
u_{13}=1
\]

Therefore:

\[
U=
\begin{bmatrix}
2&1&1\\
0&u_{22}&u_{23}\\
0&0&u_{33}
\end{bmatrix}
\]

### Step 3: Calculate the First Column of L

\[
l_{21}=\frac{4}{2}=2
\]

\[
l_{31}=\frac{-2}{2}=-1
\]

Therefore:

\[
L=
\begin{bmatrix}
1&0&0\\
2&1&0\\
-1&l_{32}&1
\end{bmatrix}
\]

### Step 4: Calculate the Second Row of U

\[
u_{22}=-6-(2)(1)
\]

\[
u_{22}=-8
\]

\[
u_{23}=0-(2)(1)
\]

\[
u_{23}=-2
\]

### Step 5: Calculate the Remaining Elements

\[
l_{32}=\frac{7-(-1)(1)}{-8}
\]

\[
l_{32}=-1
\]

Now calculate:

\[
u_{33}=2-[(-1)(1)+(-1)(-2)]
\]

\[
u_{33}=1
\]

### Step 6: Final Matrices

The lower triangular matrix is:

\[
\boxed{
L=
\begin{bmatrix}
1&0&0\\
2&1&0\\
-1&-1&1
\end{bmatrix}
}
\]

The upper triangular matrix is:

\[
\boxed{
U=
\begin{bmatrix}
2&1&1\\
0&-8&-2\\
0&0&1
\end{bmatrix}
}
\]

Verify:

\[
LU=
\begin{bmatrix}
2&1&1\\
4&-6&0\\
-2&7&2
\end{bmatrix}
=A
\]

Hence, the decomposition is correct.

## 6. Solving Linear Systems Using LU Decomposition

Consider:

\[
Ax=b
\]

Since:

\[
A=LU
\]

We can write:

\[
LUx=b
\]

Let:

\[
Ux=y
\]

Therefore:

\[
Ly=b
\]

The solution is obtained in two stages:

1. Forward substitution to solve Ly = b.
2. Backward substitution to solve Ux = y.

### Numerical Example

Consider:

\[
A=
\begin{bmatrix}
2&1&1\\
4&-6&0\\
-2&7&2
\end{bmatrix}
\]

and:

\[
b=
\begin{bmatrix}
5\\
-2\\
9
\end{bmatrix}
\]

### Step 1: Forward Substitution

Solve:

\[
Ly=b
\]

Using:

\[
L=
\begin{bmatrix}
1&0&0\\
2&1&0\\
-1&-1&1
\end{bmatrix}
\]

We get:

\[
y_1=5
\]

\[
2y_1+y_2=-2
\]

\[
y_2=-12
\]

From the third row:

\[
-y_1-y_2+y_3=9
\]

\[
-5+12+y_3=9
\]

\[
y_3=2
\]

Therefore:

\[
y=
\begin{bmatrix}
5\\
-12\\
2
\end{bmatrix}
\]

### Step 2: Backward Substitution

Solve:

\[
Ux=y
\]

Using:

\[
U=
\begin{bmatrix}
2&1&1\\
0&-8&-2\\
0&0&1
\end{bmatrix}
\]

From the third row:

\[
x_3=2
\]

From the second row:

\[
-8x_2-2(2)=-12
\]

\[
x_2=1
\]

From the first row:

\[
2x_1+x_2+x_3=5
\]

\[
2x_1+1+2=5
\]

\[
x_1=1
\]

Final solution:

\[
\boxed{x_1=1,\quad x_2=1,\quad x_3=2}
\]

## 7. Python Implementation

The following implementation uses NumPy and SciPy to perform LU Decomposition.

```python
import numpy as np
from scipy.linalg import lu, solve_triangular

A = np.array([
    [2, 1, 1],
    [4, -6, 0],
    [-2, 7, 2]
], dtype=float)

b = np.array([5, -2, 9], dtype=float)

# Perform LU Decomposition
P, L, U = lu(A)

print("Permutation Matrix P:")
print(P)

print("\nLower Triangular Matrix L:")
print(L)

print("\nUpper Triangular Matrix U:")
print(U)

# Verify A = P @ L @ U
print("\nDecomposition Verification:")
print(np.allclose(A, P @ L @ U))

# Forward substitution
y = solve_triangular(L, P.T @ b, lower=True)

# Backward substitution
x = solve_triangular(U, y)

print("\nSolution:", x)

# Verify solution
print("Ax =", A @ x)
print("b  =", b)
```

### Expected Output

```text
Decomposition Verification:
True

Solution: [1. 1. 2.]

Ax = [ 5. -2.  9.]
b  = [ 5. -2.  9.]
```

## 8. LU Decomposition from Scratch

The following implementation demonstrates Doolittle's method without pivoting.

```python
import numpy as np

def lu_decomposition(A):
    A = np.array(A, dtype=float)

    n = A.shape[0]

    L = np.eye(n)
    U = np.zeros((n, n))

    for i in range(n):

        # Calculate upper triangular matrix
        for k in range(i, n):
            total = sum(
                L[i, j] * U[j, k]
                for j in range(i)
            )

            U[i, k] = A[i, k] - total

        if np.isclose(U[i, i], 0):
            raise ValueError(
                "Zero pivot encountered. Pivoting is required."
            )

        # Calculate lower triangular matrix
        for k in range(i + 1, n):
            total = sum(
                L[k, j] * U[j, i]
                for j in range(i)
            )

            L[k, i] = (
                A[k, i] - total
            ) / U[i, i]

    return L, U


A = [
    [2, 1, 1],
    [4, -6, 0],
    [-2, 7, 2]
]

L, U = lu_decomposition(A)

print("L Matrix:")
print(L)

print("\nU Matrix:")
print(U)

print("\nVerification:")
print(np.allclose(np.array(A), L @ U))
```

This implementation assumes that non-zero pivots are available without row exchanges.

## 9. Computational Complexity

For a dense n×n matrix, LU factorization requires approximately:

\[
O(n^3)
\]

operations.

Once the matrix is factorized, each additional system with a new right-hand side can be solved using forward and backward substitution in:

\[
O(n^2)
\]

This makes LU Decomposition efficient when solving multiple systems involving the same matrix.

## 10. Applications in Machine Learning

### 10.1 Linear Regression

LU Decomposition can be used to solve linear systems arising from the normal equations of linear regression.

### 10.2 Numerical Optimization

Some optimization algorithms require repeated solutions of linear systems.

### 10.3 Scientific Computing

LU Decomposition is widely used in numerical simulations and mathematical modelling.

### 10.4 Engineering Applications

It is useful in structural analysis, electrical circuit calculations, and computational mechanics.

## 11. Advantages

- Efficient for solving multiple linear systems.
- Reduces repeated calculations.
- Provides a systematic matrix factorization method.
- Useful in scientific and numerical computing.
- Can be combined with pivoting for numerical stability.

## 12. Limitations

- Some matrices require pivoting.
- Standard LU factorization is primarily designed for square matrices.
- Dense factorization can be expensive for very large matrices.
- Numerical rounding errors may affect accuracy.
- Special treatment is required for singular matrices.

## 13. Comparison with Gaussian Elimination

| Feature | Gaussian Elimination | LU Decomposition |
|---|---|---|
| Main objective | Solve linear systems | Factorize matrices |
| Matrix transformation | Upper triangular form | Lower and upper triangular matrices |
| Substitution | Back substitution | Forward and backward substitution |
| Multiple right-hand sides | Repeated elimination may be needed | Reuse the same factorization |
| Applications | General linear systems | Repeated numerical solutions |

## 14. Practice Questions

1. Define LU Decomposition.
2. Differentiate lower and upper triangular matrices.
3. Explain Doolittle's method.
4. Explain Crout's method.
5. Find the LU decomposition of a 3×3 matrix.
6. Solve a system of linear equations using LU Decomposition.
7. Explain forward substitution.
8. Explain backward substitution.
9. Why is pivoting important in LU Decomposition?
10. Compare LU Decomposition with Gaussian Elimination.

## 15. Conclusion

LU Decomposition is a fundamental matrix factorization technique used in Linear Algebra and numerical computing.

By decomposing a matrix into lower and upper triangular matrices, it simplifies the process of solving linear systems.

It is particularly useful when multiple systems share the same coefficient matrix and is widely applied in Machine Learning, engineering, and scientific computing.

## References

- Gilbert Strang - Introduction to Linear Algebra.
- [NumPy Documentation](https://numpy.org/doc/)
- [SciPy Linear Algebra Documentation](https://docs.scipy.org/doc/scipy/reference/linalg.html)
- [MIT OpenCourseWare - Linear Algebra](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/)
