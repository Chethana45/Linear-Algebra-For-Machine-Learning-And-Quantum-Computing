# Matrix Operations

## 1. Introduction

Matrix operations are fundamental concepts in linear algebra. They involve performing mathematical operations on matrices to solve problems in mathematics, machine learning, data science, and scientific computing.

This document covers three important matrix operations:

1. Matrix Multiplication
2. Matrix Determinant
3. Matrix Inverse

---

# 2. Matrix Multiplication

## 2.1 Introduction

Matrix multiplication involves multiplying two matrices to produce a new matrix.

Let A have dimensions m × n and B have dimensions n × p.

The resulting matrix C will have dimensions m × p.

### Mathematical Representation

\[
C = AB
\]

**Condition:** The number of columns in the first matrix must equal the number of rows in the second matrix.

## 2.2 Formula

Each element of the resulting matrix is calculated as:

\[
C_{ij}=\sum_{k=1}^{n} A_{ik}B_{kj}
\]

This means multiplying corresponding elements of a row in A and a column in B, then adding the products.

## 2.3 Worked Example

Consider:

\[
A =
\begin{bmatrix}
1 & 2\\
3 & 4
\end{bmatrix}
\]

\[
B =
\begin{bmatrix}
5 & 6\\
7 & 8
\end{bmatrix}
\]

Calculate:

\[
C_{11}=(1\times5)+(2\times7)=19
\]

\[
C_{12}=(1\times6)+(2\times8)=22
\]

\[
C_{21}=(3\times5)+(4\times7)=43
\]

\[
C_{22}=(3\times6)+(4\times8)=50
\]

Final result:

\[
C =
\begin{bmatrix}
19 & 22\\
43 & 50
\end{bmatrix}
\]

## 2.4 Python Implementation Using NumPy

### Import Library

```python
import numpy as np
```

### Create Matrices

```python
A = np.array([
    [1, 2],
    [3, 4]
])

B = np.array([
    [5, 6],
    [7, 8]
])
```

### Perform Matrix Multiplication

```python
C = np.matmul(A, B)

print("Matrix Multiplication:")
print(C)
```

Alternatively:

```python
C = A @ B
print(C)
```

### Element-wise Multiplication

```python
print(A * B)
```

**Difference:**
- `A * B` performs element-wise multiplication.
- `A @ B` performs matrix multiplication.

## 2.5 Properties of Matrix Multiplication

**Associative Property**

\[
(AB)C=A(BC)
\]

**Distributive Property**

\[
A(B+C)=AB+AC
\]

**Non-Commutative Property**

\[
AB\neq BA
\]

**Identity Property**

\[
AI=IA=A
\]

**Zero Matrix Property**

\[
A\times 0=0
\]

## 2.6 Applications

- Neural network computations.
- Computer graphics transformations.
- Image processing.
- Data transformations.
- Quantum computing operations.

---

# 3. Matrix Determinant

## 3.1 Introduction

The determinant is a scalar value calculated from a square matrix.

It is represented as:

\[
\det(A) \quad \text{or} \quad |A|
\]

The determinant helps determine whether a matrix is invertible.

## 3.2 Determinant of a 2 × 2 Matrix

For:

\[
A =
\begin{bmatrix}
a & b\\
c & d
\end{bmatrix}
\]

The determinant is:

\[
\det(A)=ad-bc
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
\det(A)=(2\times5)-(3\times4)
\]

\[
=10-12
\]

\[
\boxed{\det(A)=-2}
\]

## 3.3 Determinant of a 3 × 3 Matrix

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

## 3.4 Python Implementation Using NumPy

### Import Library

```python
import numpy as np
```

### Create a Matrix

```python
A = np.array([
    [2, 3],
    [4, 5]
])
```

### Calculate Determinant

```python
det = np.linalg.det(A)

print("Determinant:")
print(det)
```

## 3.5 Properties of Determinants

1. Determinants are defined only for square matrices.
2. If the determinant is zero, the matrix is singular.
3. If the determinant is non-zero, the matrix is invertible.
4. The determinant of an identity matrix is 1.
5. The determinant of a transpose is equal to the original determinant.

\[
\det(A^T)=\det(A)
\]

6. The determinant of a product is the product of the determinants.

\[
\det(AB)=\det(A)\det(B)
\]

## 3.6 Singular and Non-Singular Matrices

### Singular Matrix

A matrix is singular if:

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
\det(A)=(1\times4)-(2\times2)=0
\]

### Non-Singular Matrix

A matrix is non-singular if:

\[
\det(A)\neq0
\]

It has an inverse.

## 3.7 Applications

- Checking whether a matrix is invertible.
- Solving systems of linear equations.
- Matrix transformations.
- Numerical computing.
- Linear algebra algorithms.

---

# 4. Matrix Inverse

## 4.1 Introduction

The inverse of a square matrix is another matrix that produces the identity matrix when multiplied by the original matrix.

The inverse is represented as:

\[
A^{-1}
\]

It satisfies:

\[
AA^{-1}=A^{-1}A=I
\]

Where I is the identity matrix.

A matrix has an inverse only when its determinant is non-zero.

## 4.2 Inverse of a 2 × 2 Matrix

For:

\[
A =
\begin{bmatrix}
a & b\\
c & d
\end{bmatrix}
\]

The inverse is:

\[
A^{-1}=
\frac{1}{ad-bc}
\begin{bmatrix}
d & -b\\
-c & a
\end{bmatrix}
\]

**Condition:**

\[
ad-bc\neq0
\]

## 4.3 Worked Example

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
\det(A)=(2\times3)-(1\times5)
\]

\[
=6-5=1
\]

Since the determinant is non-zero, the inverse exists.

### Step 2: Calculate the Inverse

\[
A^{-1}=
\frac{1}{1}
\begin{bmatrix}
3 & -1\\
-5 & 2
\end{bmatrix}
\]

Therefore:

\[
\boxed{
A^{-1}=
\begin{bmatrix}
3 & -1\\
-5 & 2
\end{bmatrix}
}
\]

### Step 3: Verify the Inverse

\[
AA^{-1}=
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

## 4.4 Python Implementation Using NumPy

### Create a Matrix

```python
import numpy as np

A = np.array([
    [2, 1],
    [5, 3]
])

print("Original Matrix:")
print(A)
```

### Calculate the Inverse

```python
if not np.isclose(np.linalg.det(A), 0):
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

## 4.5 Applications of Matrix Inverse

- Solving systems of linear equations.
- Reversing matrix transformations.
- Linear regression calculations.
- Scientific and numerical computing.
- Mathematical modelling.

---

# 5. Solving Linear Equations Using Matrix Inverse

A system of linear equations can be represented as:

\[
Ax=b
\]

Where:

- A is the coefficient matrix.
- x is the unknown variable vector.
- b is the constant vector.

If A is invertible:

\[
x=A^{-1}b
\]

### Python Implementation

```python
import numpy as np

A = np.array([
    [2, 1],
    [5, 3]
])

b = np.array([8, 18])

x = np.linalg.solve(A, b)

print("Solution:")
print(x)
```

Using `np.linalg.solve()` is generally preferable to explicitly calculating the inverse for solving linear systems.

---

# 6. Comparison of Matrix Operations

| Operation | Result | Main Purpose |
|---|---|---|
| Matrix Multiplication | Matrix | Combining matrix transformations |
| Determinant | Scalar | Checking invertibility |
| Matrix Inverse | Matrix | Reversing a matrix transformation |

# 7. Applications in Machine Learning and Quantum Computing

### Machine Learning

- Matrix multiplication is used in neural network computations.
- Matrix inverse appears in some linear regression formulations.
- Determinants are useful in probability distributions and multivariate statistics.

### Quantum Computing

- Matrix multiplication represents the sequential application of quantum gates.
- Matrix inverses represent reverse transformations.
- Determinants are useful in studying matrix properties, including unitary matrices.

# 8. Conclusion

Matrix multiplication, determinants, and matrix inverses are essential operations in linear algebra.

Matrix multiplication helps combine matrices, determinants determine whether a matrix is invertible, and matrix inverses help solve systems of linear equations.

These operations form an important mathematical foundation for machine learning, data science, numerical computing, and quantum computing.

# References

- [NumPy – Matrix Multiplication](https://numpy.org/doc/stable/reference/generated/numpy.matmul.html)
- [NumPy – Matrix Inverse](https://numpy.org/doc/stable/reference/generated/numpy.linalg.inv.html)
- [NumPy – Determinant](https://numpy.org/doc/stable/reference/generated/numpy.linalg.det.html)
- [NumPy Documentation](https://numpy.org/doc/stable/)

---

*Part of my Linear Algebra for Machine Learning and Quantum Computing learning repository.*
