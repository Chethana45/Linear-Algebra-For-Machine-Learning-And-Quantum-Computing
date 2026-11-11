
# Vector Spaces

## 1. Introduction

A vector space is a collection of vectors that can be added together and multiplied by scalars while satisfying certain mathematical rules.

Vector spaces are one of the most important concepts in linear algebra. They provide the mathematical foundation for machine learning, data science, computer graphics, and quantum computing.

A vector space can contain vectors with two, three, or even thousands of dimensions.

## 2. Definition of a Vector Space

A vector space \(V\) over a field \(F\) is a non-empty set equipped with two operations:

1. Vector addition
2. Scalar multiplication

These operations must satisfy specific properties.

For vectors \(u,v,w\in V\) and scalars \(a,b\in F\):

## 3. Properties of Vector Spaces

### 1. Closure under Addition

The sum of two vectors must also belong to the vector space.

\[
u+v\in V
\]

### 2. Commutative Property

The order of vector addition does not matter.

\[
u+v=v+u
\]

### 3. Associative Property

\[
(u+v)+w=u+(v+w)
\]

### 4. Additive Identity

There must be a zero vector such that:

\[
v+0=v
\]

### 5. Additive Inverse

For every vector, there must be an opposite vector.

\[
v+(-v)=0
\]

### 6. Closure under Scalar Multiplication

Multiplying a vector by a scalar must produce another vector in the same space.

\[
av\in V
\]

### 7. Distributive Property over Vector Addition

\[
a(u+v)=au+av
\]

### 8. Distributive Property over Scalar Addition

\[
(a+b)v=av+bv
\]

### 9. Associativity of Scalar Multiplication

\[
a(bv)=(ab)v
\]

### 10. Scalar Identity

\[
1v=v
\]

## 4. Examples of Vector Spaces

### Example 1: Two-Dimensional Real Space

\[
\mathbb{R}^2=
\left\{
\begin{bmatrix}
x\\y
\end{bmatrix}
:x,y\in\mathbb{R}
\right\}
\]

Example vectors:

\[
u=[2,3],\quad v=[4,5]
\]

Vector addition:

\[
u+v=[2+4,3+5]=[6,8]
\]

Scalar multiplication:

\[
3u=[6,9]
\]

Both operations produce vectors in \(\mathbb{R}^2\).

### Example 2: Three-Dimensional Real Space

\[
\mathbb{R}^3=
\left\{
[x,y,z]:x,y,z\in\mathbb{R}
\right\}
\]

Example:

\[
v=[2,3,4]
\]

This space is commonly used to represent positions, directions, and forces in three-dimensional geometry.

### Example 3: Polynomial Vector Space

The set of all polynomials of degree at most 2 is a vector space.

A general polynomial is:

\[
p(x)=a+bx+cx^2
\]

where \(a,b,c\in\mathbb{R}\).

### Example 4: Matrix Vector Space

The set of all \(m\times n\) real matrices forms a vector space under ordinary matrix addition and scalar multiplication.

## 5. Python Implementation Using NumPy

NumPy provides convenient operations for working with vectors and matrices.

### Import Library

```python
import numpy as np
```

### Create Vectors

```python
u = np.array([2, 3])
v = np.array([4, 5])

print("Vector u:", u)
print("Vector v:", v)
```

### Vector Addition

```python
result = u + v

print("Addition:", result)
```

Output:

```text
[6 8]
```

### Scalar Multiplication

```python
result = 3 * u

print("Scalar Multiplication:", result)
```

Output:

```text
[6 9]
```

### Verify Closure under Addition

```python
u = np.array([2, 3])
v = np.array([4, 5])

result = u + v

print("Result:", result)
print("Dimension:", result.shape)
```

## 6. Subspaces

A subspace is a subset of a vector space that is itself a vector space under the same operations.

A non-empty subset \(W\) of \(V\) is a subspace if:

1. It contains the zero vector.
2. It is closed under vector addition.
3. It is closed under scalar multiplication.

### Example

The x-axis in \(\mathbb{R}^2\) is represented by:

\[
W=\{(x,0):x\in\mathbb{R}\}
\]

It contains the zero vector and is closed under addition and scalar multiplication. Therefore, it is a subspace of \(\mathbb{R}^2\).

## 7. Applications of Vector Spaces

### Machine Learning

- Feature vectors represent data points.
- Vector spaces provide the foundation for linear regression.
- High-dimensional spaces represent complex datasets.
- Dimensionality reduction techniques operate on vector representations.

### Computer Graphics

- Represents positions and directions.
- Supports geometric transformations.
- Helps describe objects in two-dimensional and three-dimensional spaces.

### Physics

- Represents forces, velocity, and displacement.
- Provides mathematical tools for physical systems.

### Quantum Computing

- Quantum states are represented using vectors in complex vector spaces.
- Qubits are represented using vectors in a two-dimensional complex vector space.
- Quantum operations are represented using matrices and linear transformations.

## 8. Conclusion

Vector spaces provide the mathematical foundation for understanding vectors, matrices, linear transformations, and many advanced concepts in linear algebra.

They are essential in machine learning, physics, computer graphics, and quantum computing.

Understanding vector spaces makes it easier to study linear independence, basis, dimension, and matrix operations.

## References

- [NumPy Documentation](https://numpy.org/doc/stable/)
- [MIT OpenCourseWare – Linear Algebra](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/)

---

*Part of my Linear Algebra for Machine Learning and Quantum Computing learning repository.*
