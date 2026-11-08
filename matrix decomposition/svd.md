# Singular Value Decomposition (SVD)

## 1. Introduction

Singular Value Decomposition (SVD) is an important matrix decomposition technique in linear algebra. It decomposes a matrix into three simpler matrices.

SVD can be applied to both square and rectangular matrices.

It is widely used in Machine Learning, Data Science, image processing, dimensionality reduction, and data compression.

## 2. Mathematical Representation

For a matrix A of size m × n:

\[
A = U\Sigma V^T
\]

Where:

- **A:** Original matrix of size m × n.
- **U:** Left singular vector matrix of size m × m.
- **Σ (Sigma):** Diagonal matrix containing singular values.
- **Vᵀ:** Transpose of the right singular vector matrix.

The singular values are non-negative and are usually arranged in descending order.

## 3. Understanding the Three Matrices

### U – Left Singular Vectors

- Contains the left singular vectors.
- Its columns are orthonormal.
- Represents directions in the output space.

### Σ – Singular Values

- Contains singular values along its diagonal.
- Singular values indicate the importance of corresponding components.
- Larger singular values represent more significant information.

### Vᵀ – Right Singular Vectors

- Contains the transpose of the right singular vector matrix.
- Its rows are orthonormal.
- Represents directions in the input space.

## 4. Properties of SVD

1. SVD can be performed on any rectangular matrix.
2. Singular values are always non-negative.
3. Singular values are arranged in descending order.
4. U and V are orthogonal matrices for real-valued matrices.
5. SVD is useful for finding the rank of a matrix.
6. It helps in reducing the dimensions of datasets.

## 5. Python Implementation Using NumPy

NumPy provides the `numpy.linalg.svd()` function to perform Singular Value Decomposition.

### Import Libraries

```python
import numpy as np
```

### Create a Matrix

```python
A = np.array([
    [3, 2],
    [2, 3]
])

print("Original Matrix:")
print(A)
```

### Perform SVD

```python
U, S, VT = np.linalg.svd(A)

print("U Matrix:")
print(U)

print("Singular Values:")
print(S)

print("V Transpose:")
print(VT)
```

### Reconstruct the Original Matrix

NumPy returns the singular values as a one-dimensional array. We convert them into a diagonal matrix before reconstruction.

```python
Sigma = np.diag(S)

A_reconstructed = U @ Sigma @ VT

print("Reconstructed Matrix:")
print(A_reconstructed)
```

The reconstructed matrix should be approximately equal to the original matrix. Small floating-point differences may occur.

## 6. Low-Rank Approximation

One of the important applications of SVD is low-rank approximation.

Instead of using all singular values, we can retain only the largest k singular values and their corresponding singular vectors.

This produces an approximate version of the original matrix.

### Python Implementation

```python
k = 1

U_k = U[:, :k]
S_k = np.diag(S[:k])
VT_k = VT[:k, :]

A_approx = U_k @ S_k @ VT_k

print("Original Matrix:")
print(A)

print("Low-Rank Approximation:")
print(A_approx)
```

Low-rank approximation helps reduce storage requirements while preserving the most important information.

## 7. Applications of SVD

### 1. Dimensionality Reduction

SVD reduces the number of features in a dataset while retaining important information.

### 2. Image Compression

An image can be represented as a matrix. SVD helps approximate the image using fewer singular values, reducing storage requirements.

### 3. Recommendation Systems

SVD can identify hidden patterns in user-item rating matrices and help recommend products, movies, or other content.

### 4. Noise Reduction

Small singular values can sometimes represent less significant information or noise. Removing selected components can help produce a cleaner approximation.

### 5. Principal Component Analysis (PCA)

SVD is closely related to PCA and can be used to calculate principal directions in a dataset.

## 8. SVD vs LU Decomposition

| Feature | LU Decomposition | SVD |
|---|---|---|
| Decomposition | A = LU | A = UΣVᵀ |
| Matrix type | Primarily square matrices | Square and rectangular matrices |
| Main purpose | Solving linear equations | Matrix analysis and approximation |
| Components | Lower and upper triangular matrices | Singular vectors and singular values |
| Applications | Linear systems, determinants | PCA, compression, dimensionality reduction |

## 9. Conclusion

Singular Value Decomposition is a powerful matrix factorization technique that breaks a matrix into three meaningful components.

It is particularly useful in machine learning and data science because it supports dimensionality reduction, feature extraction, image compression, and low-rank approximation.

Understanding SVD provides a strong mathematical foundation for working with real-world machine learning datasets.

## References

- [NumPy – Singular Value Decomposition](https://numpy.org/doc/stable/reference/generated/numpy.linalg.svd.html)
- [Linear Algebra – SVD](https://en.wikipedia.org/wiki/Singular_value_decomposition)

---

*Part of my Linear Algebra for Machine Learning and Quantum Computing learning repository.*
