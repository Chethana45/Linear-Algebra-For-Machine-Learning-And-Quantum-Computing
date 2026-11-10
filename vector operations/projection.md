# Vector Projection

## 1. Introduction

Vector projection is a mathematical operation that projects one vector onto another vector.

It helps determine how much of one vector lies in the direction of another vector.

Vector projection is widely used in linear algebra, machine learning, physics, computer graphics, and data analysis.

## 2. Mathematical Representation

Consider two vectors A and B.

The projection of A onto B is represented as:

\[
\operatorname{proj}_B A
\]

Its formula is:

\[
\operatorname{proj}_B A =
\frac{A\cdot B}{B\cdot B}B
\]

Where:

- A is the vector being projected.
- B is the vector onto which A is projected.
- \(A\cdot B\) is the dot product.
- \(B\cdot B\) is the squared magnitude of B.

**Condition:** B must be a nonzero vector.

## 3. Scalar Projection

The scalar projection measures the signed length of A in the direction of B.

Formula:

\[
\operatorname{comp}_B A =
\frac{A\cdot B}{\|B\|}
\]

It can also be written as:

\[
\operatorname{comp}_B A=\|A\|\cos\theta
\]

## 4. Worked Example

Consider:

\[
A=[3,4]
\]

\[
B=[1,0]
\]

### Step 1: Calculate the Dot Product

\[
A\cdot B=(3\times1)+(4\times0)
\]

\[
=3
\]

### Step 2: Calculate the Squared Magnitude of B

\[
B\cdot B=(1\times1)+(0\times0)
\]

\[
=1
\]

### Step 3: Calculate the Projection

\[
\operatorname{proj}_B A =
\frac{3}{1}[1,0]
\]

\[
\boxed{[3,0]}
\]

Therefore, the projection of A onto B is [3, 0].

## 5. Python Implementation Using NumPy

### Import Library

```python
import numpy as np
```

### Create Vectors

```python
A = np.array([3, 4])
B = np.array([1, 0])

print("Vector A:", A)
print("Vector B:", B)
```

### Calculate Vector Projection

```python
projection = (np.dot(A, B) / np.dot(B, B)) * B

print("Projection of A onto B:")
print(projection)
```

### Calculate Scalar Projection

```python
scalar_projection = np.dot(A, B) / np.linalg.norm(B)

print("Scalar Projection:")
print(scalar_projection)
```

### Calculate the Perpendicular Component

The perpendicular component is the difference between the original vector and its projection.

\[
A_\perp=A-\operatorname{proj}_B A
\]

```python
perpendicular = A - projection

print("Perpendicular Component:")
print(perpendicular)
```

## 6. Geometric Interpretation

Vector projection separates a vector into two components:

1. Parallel component – the part of A in the direction of B.
2. Perpendicular component – the part of A perpendicular to B.

\[
A=\operatorname{proj}_B A+A_\perp
\]

The projection represents the shadow of vector A on the direction of vector B.

## 7. Properties of Vector Projection

1. The projection lies along the direction of vector B.
2. The projection is zero when A is perpendicular to B.
3. Projecting a vector onto itself gives the same vector.

\[
\operatorname{proj}_A A=A
\]

4. The perpendicular component is orthogonal to B.

\[
(A-\operatorname{proj}_B A)\cdot B=0
\]

## 8. Applications

### 1. Machine Learning

Projection is used in dimensionality reduction techniques and feature transformations.

### 2. Linear Regression

Predictions in least-squares regression can be interpreted as projections onto the column space of a matrix.

### 3. Computer Graphics

Used to calculate shadows, lighting, and geometric relationships.

### 4. Physics

Used to resolve forces and velocities into components along particular directions.

### 5. Data Analysis

Projection helps represent high-dimensional data in lower-dimensional spaces.

### 6. Quantum Computing

Projection operators are used in the mathematical description of quantum measurements.

## 9. Conclusion

Vector projection is an important operation that determines the component of one vector along another vector.

It connects dot products, vector magnitudes, and geometric relationships. It is particularly useful in machine learning, physics, computer graphics, and numerical analysis.

## References

- [NumPy – Dot Product](https://numpy.org/doc/stable/reference/generated/numpy.dot.html)
- [NumPy – Vector Norm](https://numpy.org/doc/stable/reference/generated/numpy.linalg.norm.html)
- [NumPy – Linear Algebra](https://numpy.org/doc/stable/reference/routines.linalg.html)

---

*Part of my Linear Algebra for Machine Learning and Quantum Computing learning repository.*
