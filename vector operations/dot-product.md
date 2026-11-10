
# Dot Product of Vectors

## 1. Introduction

The dot product, also called the scalar product, is an operation that takes two vectors and produces a single scalar value.

It measures how much two vectors point in the same direction.

The dot product is widely used in linear algebra, machine learning, physics, computer graphics, and quantum computing.

## 2. Mathematical Representation

For two vectors:

\[
A = [a_1,a_2,\ldots,a_n]
\]

\[
B = [b_1,b_2,\ldots,b_n]
\]

Their dot product is:

\[
A \cdot B = a_1b_1+a_2b_2+\cdots+a_nb_n
\]

Or:

\[
A \cdot B = \sum_{i=1}^{n}a_ib_i
\]

The result is always a scalar.

## 3. Worked Example

Consider:

\[
A = [2,3]
\]

\[
B = [4,5]
\]

Calculate the dot product:

\[
A \cdot B = (2\times4)+(3\times5)
\]

\[
=8+15
\]

\[
\boxed{A\cdot B=23}
\]

## 4. Geometric Interpretation

The dot product can also be calculated using the angle between two vectors.

\[
A\cdot B = |A||B|\cos\theta
\]

Where:

- \(|A|\) is the magnitude of vector A.
- \(|B|\) is the magnitude of vector B.
- \(\theta\) is the angle between the vectors.

### Important Cases

**1. Same Direction**

If the angle is 0°:

\[
\cos 0^\circ=1
\]

The dot product is positive and maximum for fixed magnitudes.

**2. Perpendicular Vectors**

If the angle is 90°:

\[
\cos 90^\circ=0
\]

\[
A\cdot B=0
\]

**3. Opposite Directions**

If the angle is 180°:

\[
\cos 180^\circ=-1
\]

The dot product is negative for nonzero vectors.

## 5. Python Implementation Using NumPy

### Import Library

```python
import numpy as np
```

### Create Vectors

```python
A = np.array([2, 3])
B = np.array([4, 5])

print("Vector A:", A)
print("Vector B:", B)
```

### Calculate Dot Product

```python
result = np.dot(A, B)

print("Dot Product:", result)
```

Alternatively:

```python
result = A @ B
print(result)
```

### Calculate Angle Between Vectors

```python
dot = np.dot(A, B)

magnitude_A = np.linalg.norm(A)
magnitude_B = np.linalg.norm(B)

cos_theta = dot / (magnitude_A * magnitude_B)

angle = np.degrees(np.arccos(np.clip(cos_theta, -1, 1)))

print("Angle:", angle)
```

## 6. Properties of Dot Product

### 1. Commutative Property

\[
A\cdot B=B\cdot A
\]

### 2. Distributive Property

\[
A\cdot(B+C)=A\cdot B+A\cdot C
\]

### 3. Scalar Multiplication

\[
(kA)\cdot B=k(A\cdot B)
\]

### 4. Self Dot Product

\[
A\cdot A=|A|^2
\]

### 5. Orthogonality

Two nonzero vectors are perpendicular if:

\[
A\cdot B=0
\]

## 7. Applications

### Machine Learning

- Measures similarity between feature vectors.
- Used in linear regression and neural networks.
- Helps calculate weighted sums.

### Information Retrieval

Dot products are used to compare vector representations of documents and queries.

### Physics

Used to calculate work done by a force:

\[
W=F\cdot d
\]

### Computer Graphics

Used in lighting calculations and determining angles between surface normals and light directions.

### Quantum Computing

Inner products help calculate relationships between quantum states and measurement probabilities.

## 8. Conclusion

The dot product is an important vector operation that produces a scalar value from two vectors.

It helps measure directional similarity, calculate angles, and identify perpendicular vectors. It forms the foundation for many mathematical operations in machine learning, physics, and quantum computing.

## References

- [NumPy – Dot Product](https://numpy.org/doc/stable/reference/generated/numpy.dot.html)
- [NumPy – Linear Algebra](https://numpy.org/doc/stable/reference/routines.linalg.html)

---

*Part of my Linear Algebra for Machine Learning and Quantum Computing learning repository.*
