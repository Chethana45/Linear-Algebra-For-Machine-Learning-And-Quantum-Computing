# Basis and Dimension

## 1. Introduction

Basis and dimension are important concepts in vector spaces.

A basis is a set of linearly independent vectors that can generate every vector in a particular vector space.

Dimension represents the number of vectors in a basis.

## 2. Basis of a Vector Space

A set of vectors forms a basis if it satisfies two conditions:

1. The vectors are linearly independent.
2. The vectors span the entire vector space.

### Example

Consider the standard basis of \(\mathbb{R}^2\):

\[
v_1=[1,0]
\]

\[
v_2=[0,1]
\]

Any vector in \(\mathbb{R}^2\) can be represented as:

\[
[a,b]=a[1,0]+b[0,1]
\]

Therefore, these vectors form a basis for \(\mathbb{R}^2\).

## 3. Dimension of a Vector Space

The dimension of a vector space is the number of vectors in any basis of that space.

Examples:

| Vector Space | Dimension |
|---|---:|
| \(\mathbb{R}^2\) | 2 |
| \(\mathbb{R}^3\) | 3 |
| \(\mathbb{R}^4\) | 4 |
| Polynomials of degree at most 2 | 3 |

## 4. Standard Basis

The standard basis vectors are:

For \(\mathbb{R}^2\):

\[
\{[1,0],[0,1]\}
\]

For \(\mathbb{R}^3\):

\[
\{[1,0,0],[0,1,0],[0,0,1]\}
\]

Each basis vector represents an independent coordinate direction.

## 5. Python Implementation Using NumPy

```python
import numpy as np

A = np.array([
    [1, 0],
    [0, 1]
])

rank = np.linalg.matrix_rank(A)

print("Basis vectors:")
print(A)

print("Dimension:", rank)
```

### Example with Three Vectors

```python
B = np.array([
    [1, 0, 1],
    [0, 1, 1]
])

print("Rank:", np.linalg.matrix_rank(B))
```

The three columns span \(\mathbb{R}^2\), but they are linearly dependent. A basis can be formed using the first two columns.

## 6. Applications

### Machine Learning
- Understanding feature dimensions.
- Representing data using independent features.
- Reducing redundant dimensions.

### Computer Graphics
- Defining coordinate systems.
- Representing positions and transformations.

### Quantum Computing
- Representing quantum states using basis vectors.
- Understanding computational basis states such as \(|0\rangle\) and \(|1\rangle\).

## 7. Conclusion

A basis provides a minimal set of independent vectors that can represent every vector in a space. Dimension tells us how many independent directions are needed to describe that space.

These concepts are essential in linear algebra, machine learning, and quantum computing.

## References
- NumPy: https://numpy.org/doc/stable/reference/generated/numpy.linalg.matrix_rank.html
