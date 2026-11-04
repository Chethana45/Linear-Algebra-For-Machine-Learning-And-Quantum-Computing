# Tensors in Linear Algebra and Machine Learning

## 1. Introduction

A tensor is a mathematical object that generalizes scalars, vectors, and matrices to higher dimensions.

Tensors are widely used in machine learning, deep learning, computer vision, scientific computing, and quantum computing.

They provide an efficient way to represent and process multidimensional numerical data.

## 2. Understanding Tensor Dimensions

Tensors can be classified based on their number of dimensions, also called their order or rank in common programming terminology.

| Mathematical Object | Number of Dimensions | Example |
|---|---:|---|
| Scalar | 0D | 5 |
| Vector | 1D | [1, 2, 3] |
| Matrix | 2D | [[1, 2], [3, 4]] |
| 3D Tensor | 3D | Collection of matrices |
| Higher-order Tensor | 4D or more | Collection of 3D tensors |

Note: In this repository, tensor rank refers to the number of array axes (dimensions), as commonly used in NumPy and deep learning libraries.

## 3. Scalar as a 0D Tensor

A scalar contains a single numerical value.

Example:

\[
A=5
\]

It has no axes or dimensions.

In Python:

```python
import numpy as np

scalar = np.array(5)

print(scalar)
print(scalar.ndim)
print(scalar.shape)
```

Output:

```text
5
0
()
```

## 4. Vector as a 1D Tensor

A vector contains a sequence of values.

Example:

\[
v=[1,2,3]
\]

It has one dimension.

Python:

```python
vector = np.array([1, 2, 3])

print(vector)
print("Dimensions:", vector.ndim)
print("Shape:", vector.shape)
```

Output:

```text
[1 2 3]
Dimensions: 1
Shape: (3,)
```

## 5. Matrix as a 2D Tensor

A matrix is a rectangular arrangement of numerical values in rows and columns.

Example:

\[
A=
\begin{bmatrix}
1&2\\
3&4
\end{bmatrix}
\]

It has two dimensions.

Python:

```python
matrix = np.array([
    [1, 2],
    [3, 4]
])

print(matrix)
print("Dimensions:", matrix.ndim)
print("Shape:", matrix.shape)
```

Output:

```text
[[1 2]
 [3 4]]
Dimensions: 2
Shape: (2, 2)
```

## 6. Three-Dimensional Tensors

A 3D tensor can be understood as a collection of matrices.

Example:

\[
T=
\begin{bmatrix}
\begin{bmatrix}1&2\\3&4\end{bmatrix}\\
\begin{bmatrix}5&6\\7&8\end{bmatrix}
\end{bmatrix}
\]

Its shape is:

\[
(2,2,2)
\]

This means:

- 2 matrices
- Each matrix has 2 rows
- Each matrix has 2 columns

Python:

```python
tensor_3d = np.array([
    [[1, 2], [3, 4]],
    [[5, 6], [7, 8]]
])

print(tensor_3d)
print("Dimensions:", tensor_3d.ndim)
print("Shape:", tensor_3d.shape)
```

Output:

```text
Dimensions: 3
Shape: (2, 2, 2)
```

## 7. Four-Dimensional Tensors

A 4D tensor can represent a batch of 3D data.

One common example is a batch of color images.

A batch of images can have the shape:

\[
(N,H,W,C)
\]

Where:

- N = Number of images
- H = Image height
- W = Image width
- C = Number of color channels

For example:

\[
(32,224,224,3)
\]

This represents 32 RGB images, each with a height and width of 224 pixels.

Some deep learning frameworks use a different channel ordering, such as:

\[
(N,C,H,W)
\]

Always check the framework's expected input format.

## 8. Tensor Operations

Tensors support several mathematical and computational operations.

### A. Tensor Addition

Two tensors with compatible shapes can be added element-wise.

```python
A = np.array([1, 2, 3])
B = np.array([4, 5, 6])

print(A + B)
```

Output:

```text
[5 7 9]
```

### B. Tensor Multiplication

Element-wise multiplication:

```python
A = np.array([1, 2, 3])
B = np.array([4, 5, 6])

print(A * B)
```

Output:

```text
[ 4 10 18]
```

### C. Tensor Reshaping

Reshaping changes the dimensions of a tensor without changing its elements.

```python
A = np.array([1, 2, 3, 4, 5, 6])

reshaped = A.reshape(2, 3)

print(reshaped)
```

Output:

```text
[[1 2 3]
 [4 5 6]]
```

### D. Transpose

For a 2D tensor (matrix), transpose swaps rows and columns.

```python
A = np.array([
    [1, 2],
    [3, 4]
])

print(A.T)
```

Output:

```text
[[1 3]
 [2 4]]
```

## 9. Applications in Machine Learning

Tensors are the primary data structures used by many machine learning and deep learning frameworks.

### A. Image Processing

An RGB image can be represented as a 3D tensor:

\[
Height \times Width \times Channels
\]

Each pixel contains three values corresponding to red, green, and blue channels.

### B. Neural Networks

Neural networks use tensors to represent:

- Input data
- Weights
- Biases
- Activations
- Gradients

Matrix and tensor operations are performed throughout the forward and backward passes.

### C. Natural Language Processing

Text can be represented as sequences of numerical vectors.

For a batch of tokenized sequences, an embedding tensor may have the shape:

\[
(B,L,D)
\]

Where:

- B = Batch size
- L = Sequence length
- D = Embedding dimension

### D. Deep Learning Frameworks

Popular frameworks that support tensor operations include:

- PyTorch
- TensorFlow
- JAX

## 10. Applications in Quantum Computing

Tensors also play an important role in quantum computing.

### A. Quantum States

A single qubit can be represented using a two-dimensional complex vector:

\[
|\psi\rangle =
\alpha|0\rangle+\beta|1\rangle
\]

### B. Tensor Products

Tensor products combine the state spaces of multiple quantum systems.

For two qubits:

\[
|0\rangle =
\begin{bmatrix}
1\\0
\end{bmatrix},
\quad
|1\rangle =
\begin{bmatrix}
0\\1
\end{bmatrix}
\]

Their tensor product is:

\[
|0\rangle\otimes|1\rangle =
\begin{bmatrix}
1\\0
\end{bmatrix}
\otimes
\begin{bmatrix}
0\\1
\end{bmatrix}
=
\begin{bmatrix}
0\\1\\0\\0
\end{bmatrix}
\]

This represents the two-qubit computational basis state \(|01\rangle\).

Tensor products are essential for describing multi-qubit systems and quantum operations.

## 11. Complete Python Demonstration

```python
import numpy as np

# 0D Tensor - Scalar
scalar = np.array(5)

# 1D Tensor - Vector
vector = np.array([1, 2, 3])

# 2D Tensor - Matrix
matrix = np.array([
    [1, 2],
    [3, 4]
])

# 3D Tensor
tensor_3d = np.array([
    [[1, 2], [3, 4]],
    [[5, 6], [7, 8]]
])

# Display tensor information
tensors = {
    "Scalar": scalar,
    "Vector": vector,
    "Matrix": matrix,
    "3D Tensor": tensor_3d
}

for name, tensor in tensors.items():
    print(f"\n{name}")
    print("Value:\n", tensor)
    print("Dimensions:", tensor.ndim)
    print("Shape:", tensor.shape)
```

## 12. Key Takeaways

- Tensors generalize scalars, vectors, and matrices.
- A scalar is a 0D tensor.
- A vector is a 1D tensor.
- A matrix is a 2D tensor.
- Higher-dimensional tensors represent more complex data.
- Tensor shapes describe the size along each axis.
- Deep learning frameworks use tensors for data and model computations.
- Tensor products help represent combined quantum systems.

---

**Next Topics:** Tensor Operations, Tensor Products, and Their Applications in Machine Learning and Quantum Computing.
