# Scalars and Vectors

## 1. Introduction

Scalars and vectors are fundamental mathematical objects in linear algebra. They are widely used in physics, engineering, machine learning, computer graphics, and quantum computing.

They provide a mathematical way to represent quantities, data, directions, and transformations.

## 2. Scalars

A **scalar** is a single numerical value that represents magnitude only.

It does not have direction.

### Examples

- Temperature: 30°C
- Weight: 56 kg
- Learning rate: 0.01
- Distance: 100 metres
- Model accuracy: 95%

### Mathematical Representation

A scalar is generally represented using a lowercase letter.

\[
a = 5
\]

\[
b = 3.14
\]

Scalars can be real or complex numbers.

### Scalar Operations

Given two scalars:

\[
a=5,\quad b=3
\]

| Operation | Result |
|---|---|
| Addition | \(a+b=8\) |
| Subtraction | \(a-b=2\) |
| Multiplication | \(a \times b=15\) |
| Division | \(a/b=1.667\) |

## 3. Vectors

A **vector** is an ordered collection of numerical values. In elementary geometry, a vector represents both magnitude and direction.

In linear algebra, a vector is represented as an ordered list of components.

For example:

\[
v =
\begin{bmatrix}
2\\
3
\end{bmatrix}
\]

This is a two-dimensional column vector.

Another example:

\[
u =
\begin{bmatrix}
2\\
4\\
6
\end{bmatrix}
\]

This is a three-dimensional column vector.

### Types of Vectors

1. Row Vector

\[
v = [2\quad 3\quad 4]
\]

2. Column Vector

\[
v =
\begin{bmatrix}
2\\
3\\
4
\end{bmatrix}
\]

3. Zero Vector

\[
0 =
\begin{bmatrix}
0\\
0
\end{bmatrix}
\]

4. Unit Vector

A vector whose magnitude is exactly 1.

## 4. Magnitude of a Vector

The magnitude or Euclidean norm measures the length of a vector.

For a two-dimensional vector:

\[
v =
\begin{bmatrix}
x\\
y
\end{bmatrix}
\]

Its magnitude is:

\[
\|v\| = \sqrt{x^2+y^2}
\]

### Example

Consider:

\[
v =
\begin{bmatrix}
3\\
4
\end{bmatrix}
\]

\[
\|v\| = \sqrt{3^2+4^2}
\]

\[
= \sqrt{9+16} = 5
\]

Therefore, the magnitude is 5.

## 5. Vector Addition

Two vectors of the same dimension can be added by adding their corresponding components.

Let:

\[
a =
\begin{bmatrix}
2\\
3
\end{bmatrix},
\quad
b =
\begin{bmatrix}
4\\
5
\end{bmatrix}
\]

Then:

\[
a+b =
\begin{bmatrix}
2+4\\
3+5
\end{bmatrix}
=
\begin{bmatrix}
6\\
8
\end{bmatrix}
\]

## 6. Scalar Multiplication of a Vector

A scalar can multiply every component of a vector.

Let:

\[
a =
\begin{bmatrix}
2\\
3
\end{bmatrix}
\]

Multiplying by 3:

\[
3a =
\begin{bmatrix}
6\\
9
\end{bmatrix}
\]

This changes the magnitude of the vector and may reverse its direction if the scalar is negative.

## 7. Dot Product

The dot product is an operation that takes two vectors and produces a scalar.

For two vectors:

\[
a =
\begin{bmatrix}
a_1\\a_2\\a_3
\end{bmatrix},
\quad
b =
\begin{bmatrix}
b_1\\b_2\\b_3
\end{bmatrix}
\]

The dot product is:

\[
a \cdot b = a_1b_1+a_2b_2+a_3b_3
\]

### Example

\[
a =
\begin{bmatrix}
1\\2\\3
\end{bmatrix},
\quad
b =
\begin{bmatrix}
4\\5\\6
\end{bmatrix}
\]

\[
a\cdot b = (1)(4)+(2)(5)+(3)(6)
\]

\[
=4+10+18=32
\]

### Geometric Interpretation

The dot product can also be expressed as:

\[
a\cdot b = \|a\|\|b\|\cos\theta
\]

where \(\theta\) is the angle between the vectors.

If the dot product is zero, two nonzero real vectors are orthogonal.

## 8. Applications in Machine Learning

Scalars and vectors are essential in machine learning.

### Feature Representation

A data sample can be represented as a vector.

For example, a house may be represented using:

\[
x =
\begin{bmatrix}
1500\\
3\\
2
\end{bmatrix}
\]

Where:

- 1500 = area in square feet
- 3 = number of bedrooms
- 2 = number of bathrooms

### Model Parameters

A machine learning model can use a weight vector:

\[
w =
\begin{bmatrix}
0.5\\
0.3\\
0.2
\end{bmatrix}
\]

A simple linear model computes:

\[
y=w^Tx+b
\]

Here, the vector stores model weights and the scalar \(b\) represents the bias.

### Other Applications

- Word embeddings in Natural Language Processing
- Feature vectors in classification
- Gradient vectors in optimization
- Similarity calculations using dot products
- Representing data points in multidimensional spaces

## 9. Applications in Quantum Computing

Vectors also play an important role in quantum computing.

A quantum state is mathematically represented as a vector in a complex vector space.

For example, the computational basis states of a single qubit are:

\[
|0\rangle =
\begin{bmatrix}
1\\0
\end{bmatrix}
\]

\[
|1\rangle =
\begin{bmatrix}
0\\1
\end{bmatrix}
\]

A general single-qubit pure state can be represented as:

\[
|\psi\rangle =
\alpha|0\rangle+\beta|1\rangle
\]

where \(\alpha\) and \(\beta\) are complex amplitudes satisfying:

\[
|\alpha|^2+|\beta|^2=1
\]

This demonstrates how vector mathematics forms the foundation of quantum state representation.

## 10. Python Implementation Using NumPy

```python
import numpy as np

# Scalar
a = 5

# Vectors
v1 = np.array([2, 3])
v2 = np.array([4, 5])

# Vector addition
print("Addition:", v1 + v2)

# Scalar multiplication
print("Scalar Multiplication:", 3 * v1)

# Dot product
print("Dot Product:", np.dot(v1, v2))

# Magnitude
print("Magnitude:", np.linalg.norm(v1))
```

### Expected Output

```text
Addition: [6 8]
Scalar Multiplication: [6 9]
Dot Product: 23
Magnitude: 3.605551275463989
```

## 11. Key Takeaways

- A scalar represents a single numerical value.
- A vector represents an ordered collection of components.
- Vector magnitude measures its length.
- Vector addition combines corresponding components.
- Scalar multiplication scales a vector.
- The dot product produces a scalar.
- Vectors are used to represent data and model parameters in machine learning.
- Quantum states are represented using complex vectors.

---

**Next Topic:** Tensors – Generalizing Scalars, Vectors, and Matrices into Higher Dimensions.
