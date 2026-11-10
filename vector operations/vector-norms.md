# Vector Norms

## 1. Introduction

A vector norm is a mathematical function that measures the length or magnitude of a vector.

It helps determine how large a vector is, regardless of its direction.

Vector norms are widely used in linear algebra, machine learning, optimization, statistics, and numerical computing.

## 2. Mathematical Representation

For a vector:

\[
A=[a_1,a_2,\ldots,a_n]
\]

The norm is represented as:

\[
\|A\|
\]

Different types of norms measure vector magnitude in different ways.

## 3. Types of Vector Norms

### 3.1 L1 Norm (Manhattan Norm)

The L1 norm is the sum of the absolute values of all vector elements.

Formula:

\[
\|A\|_1=\sum_{i=1}^{n}|a_i|
\]

Example:

\[
A=[3,-4]
\]

\[
\|A\|_1=|3|+|-4|
\]

\[
=3+4=7
\]

### 3.2 L2 Norm (Euclidean Norm)

The L2 norm calculates the ordinary straight-line length of a vector.

Formula:

\[
\|A\|_2=\sqrt{\sum_{i=1}^{n}a_i^2}
\]

Example:

\[
A=[3,4]
\]

\[
\|A\|_2=\sqrt{3^2+4^2}
\]

\[
=\sqrt{9+16}
\]

\[
\boxed{5}
\]

### 3.3 L∞ Norm (Maximum Norm)

The L-infinity norm returns the largest absolute value among the vector elements.

Formula:

\[
\|A\|_\infty=\max_i |a_i|
\]

Example:

\[
A=[3,-7,2]
\]

\[
\|A\|_\infty=7
\]

## 4. Python Implementation Using NumPy

### Import Library

```python
import numpy as np
```

### Create a Vector

```python
A = np.array([3, -4, 2])

print("Vector:", A)
```

### Calculate L1 Norm

```python
l1 = np.linalg.norm(A, ord=1)

print("L1 Norm:", l1)
```

### Calculate L2 Norm

```python
l2 = np.linalg.norm(A, ord=2)

print("L2 Norm:", l2)
```

### Calculate L∞ Norm

```python
linf = np.linalg.norm(A, ord=np.inf)

print("L-infinity Norm:", linf)
```

## 5. Comparison of Vector Norms

For the vector:

\[
A=[3,-4]
\]

| Norm | Formula | Result |
|---|---|---:|
| L1 | \(|3|+|-4|\) | 7 |
| L2 | \(\sqrt{3^2+(-4)^2}\) | 5 |
| L∞ | \(\max(3,4)\) | 4 |

## 6. Properties of Vector Norms

A valid vector norm satisfies the following properties:

### 1. Non-Negativity

\[
\|A\|\geq0
\]

### 2. Definiteness

\[
\|A\|=0 \iff A=0
\]

### 3. Absolute Homogeneity

\[
\|kA\|=|k|\|A\|
\]

### 4. Triangle Inequality

\[
\|A+B\|\leq\|A\|+\|B\|
\]

## 7. Applications in Machine Learning

### 1. Regularization

- L1 regularization encourages sparse model parameters.
- L2 regularization penalizes large model weights.

### 2. Distance Calculation

Euclidean distance is used to measure the distance between data points.

### 3. Optimization

Norms help measure errors and determine convergence in optimization algorithms.

### 4. Neural Networks

Norms are used in weight regularization and gradient analysis.

### 5. Data Normalization

Vector normalization scales vectors to a standard magnitude.

## 8. Vector Normalization

Vector normalization converts a vector into a unit vector by dividing each element by its norm.

Formula:

\[
\hat A=\frac{A}{\|A\|_2}
\]

Example:

\[
A=[3,4]
\]

\[
\|A\|_2=5
\]

Normalized vector:

\[
\hat A=[3/5,4/5]
\]

\[
\hat A=[0.6,0.8]
\]

### Python Implementation

```python
A = np.array([3, 4])

normalized = A / np.linalg.norm(A)

print("Normalized Vector:", normalized)
print("Magnitude:", np.linalg.norm(normalized))
```

## 9. Conclusion

Vector norms provide different ways to measure the magnitude of vectors.

L1, L2, and L-infinity norms are important in machine learning, optimization, and numerical computing. Understanding these norms is essential for working with vector spaces and mathematical models.

## References

- [NumPy – Vector Norm](https://numpy.org/doc/stable/reference/generated/numpy.linalg.norm.html)
- [NumPy – Linear Algebra](https://numpy.org/doc/stable/reference/routines.linalg.html)

---

*Part of my Linear Algebra for Machine Learning and Quantum Computing learning repository.*
