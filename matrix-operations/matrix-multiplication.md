# Matrix Multiplication

## 1. Introduction

Matrix multiplication is a fundamental operation in linear algebra. It involves multiplying two matrices to produce a new matrix.

It is widely used in machine learning, computer graphics, scientific computing, and data analysis.

## 2. Mathematical Representation

Let A be a matrix of size m × n and B be a matrix of size n × p.

Their product is:

\[
C = AB
\]

The resulting matrix C has dimensions m × p.

**Important condition:** The number of columns in the first matrix must equal the number of rows in the second matrix.

## 3. How Matrix Multiplication Works

Each element in the resulting matrix is calculated by multiplying corresponding elements of a row in the first matrix and a column in the second matrix, then adding the products.

\[
C_{ij} = \sum_{k=1}^{n} A_{ik}B_{kj}
\]

## 4. Worked Example

Consider two matrices:

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

Multiply A and B:

\[
C = AB
\]

Calculate each element:

\[
C_{11} = (1 \times 5) + (2 \times 7) = 19
\]

\[
C_{12} = (1 \times 6) + (2 \times 8) = 22
\]

\[
C_{21} = (3 \times 5) + (4 \times 7) = 43
\]

\[
C_{22} = (3 \times 6) + (4 \times 8) = 50
\]

Final result:

\[
C =
\begin{bmatrix}
19 & 22\\
43 & 50
\end{bmatrix}
\]

## 5. Python Implementation Using NumPy

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

print("Matrix A:")
print(A)

print("Matrix B:")
print(B)
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

### Element-wise Multiplication vs Matrix Multiplication

NumPy supports two different operations.

**Element-wise multiplication:**

```python
print(A * B)
```

Result:

```text
[[ 5 12]
 [21 32]]
```

**Matrix multiplication:**

```python
print(A @ B)
```

Result:

```text
[[19 22]
 [43 50]]
```

The `*` operator multiplies corresponding elements, whereas `@` performs matrix multiplication.

## 6. Properties of Matrix Multiplication

### 1. Associative Property

\[
(AB)C = A(BC)
\]

### 2. Distributive Property

\[
A(B+C) = AB+AC
\]

### 3. Non-Commutative Property

\[
AB \neq BA
\]

Matrix multiplication is generally not commutative.

### 4. Identity Property

\[
AI = IA = A
\]

### 5. Zero Matrix Property

\[
A \times 0 = 0
\]

## 7. Applications of Matrix Multiplication

### 1. Machine Learning

Used in neural networks to calculate weighted sums and transform input features.

### 2. Computer Graphics

Used for rotation, translation, scaling, and other geometric transformations.

### 3. Data Science

Used to process and transform large datasets.

### 4. Image Processing

Images can be represented as matrices, and matrix operations help process image data.

### 5. Quantum Computing

Matrix multiplication is used to represent quantum gates and transformations of quantum states.

## 8. Conclusion

Matrix multiplication is one of the most important operations in linear algebra. It provides the foundation for many machine learning algorithms, neural networks, computer graphics applications, and quantum computing operations.

Understanding matrix dimensions, multiplication rules, and properties is essential for working with matrices efficiently.

## References

- [NumPy – Matrix Multiplication](https://numpy.org/doc/stable/reference/generated/numpy.matmul.html)
- [NumPy Documentation](https://numpy.org/doc/stable/)

---

*Part of my Linear Algebra for Machine Learning and Quantum Computing learning repository.*
