# Eigenvalues and Eigenvectors

## 1. Introduction

Eigenvalues and eigenvectors are important concepts in linear algebra that help us understand how matrices transform vectors.

They are widely used in:

- Machine Learning
- Principal Component Analysis (PCA)
- Dimensionality Reduction
- Computer Vision
- Quantum Computing
- Stability Analysis
- Scientific Computing

The main idea is to identify special vectors whose direction does not change when a matrix transformation is applied. Their magnitude may change, but their direction remains the same (or reverses).

## 2. What is an Eigenvector?

An eigenvector is a non-zero vector that changes only in magnitude, not in direction, when multiplied by a square matrix.

Consider a square matrix \(A\) and a non-zero vector \(v\).

If:

\[
Av = \lambda v
\]

then \(v\) is an eigenvector of matrix \(A\).

Here:

- \(A\) = Square matrix
- \(v\) = Eigenvector
- \(\lambda\) = Eigenvalue

## 3. What is an Eigenvalue?

An eigenvalue is a scalar that tells us how much an eigenvector is scaled when a matrix transformation is applied.

From:

\[
Av = \lambda v
\]

The eigenvalue \(\lambda\) determines the scaling factor.

- If \(\lambda > 1\), the vector is stretched.
- If \(0 < \lambda < 1\), the vector is compressed.
- If \(\lambda < 0\), its direction is reversed as well as scaled.
- If \(\lambda = 0\), the vector is mapped to the zero vector.

## 4. Finding Eigenvalues

Starting with the eigenvalue equation:

\[
Av = \lambda v
\]

Rearrange:

\[
Av-\lambda v=0
\]

Using the identity matrix \(I\):

\[
(A-\lambda I)v=0
\]

For a non-zero solution to exist:

\[
\boxed{\det(A-\lambda I)=0}
\]

This is called the characteristic equation.

Solving this equation gives the eigenvalues.

## 5. Finding Eigenvectors

After finding the eigenvalues, substitute each eigenvalue into:

\[
(A-\lambda I)v=0
\]

Then solve the resulting homogeneous system to find the corresponding non-zero eigenvectors.

## 6. Worked Example

Consider the matrix:

\[
A=
\begin{bmatrix}
4&1\\
2&3
\end{bmatrix}
\]

### Step 1: Form the characteristic equation

\[
\det(A-\lambda I)=0
\]

\[
\begin{vmatrix}
4-\lambda&1\\
2&3-\lambda
\end{vmatrix}=0
\]

### Step 2: Calculate the determinant

\[
(4-\lambda)(3-\lambda)-2=0
\]

\[
12-7\lambda+\lambda^2-2=0
\]

\[
\lambda^2-7\lambda+10=0
\]

Factorizing:

\[
(\lambda-5)(\lambda-2)=0
\]

Therefore:

\[
\boxed{\lambda_1=5,\quad \lambda_2=2}
\]

### Step 3: Find the eigenvector for \(\lambda=5\)

\[
(A-5I)v=0
\]

\[
\begin{bmatrix}
-1&1\\
2&-2
\end{bmatrix}
\begin{bmatrix}
x\\y
\end{bmatrix}=0
\]

From the first equation:

\[
-x+y=0
\]

\[
y=x
\]

One eigenvector is:

\[
\boxed{
v_1=
\begin{bmatrix}
1\\1
\end{bmatrix}
}
\]

### Step 4: Find the eigenvector for \(\lambda=2\)

\[
(A-2I)v=0
\]

\[
\begin{bmatrix}
2&1\\
2&1
\end{bmatrix}
\begin{bmatrix}
x\\y
\end{bmatrix}=0
\]

\[
2x+y=0
\]

\[
y=-2x
\]

One eigenvector is:

\[
\boxed{
v_2=
\begin{bmatrix}
1\\-2
\end{bmatrix}
}
\]

### Final Answer

| Eigenvalue | Corresponding Eigenvector |
|---|---|
| 5 | [1, 1] |
| 2 | [1, -2] |

## 7. Geometric Interpretation

A matrix represents a linear transformation that can rotate, stretch, compress, or reflect vectors.

Eigenvectors are special directions that remain unchanged in direction after the transformation.

The eigenvalue describes the scaling along that direction.

Understanding this geometric interpretation helps explain why eigenvalues are useful in machine learning and other computational fields.

## 8. Important Properties

For an \(n \times n\) matrix:

**1. Sum of eigenvalues**

The sum of eigenvalues, counting algebraic multiplicity, equals the trace of the matrix.

\[
\sum \lambda_i = \operatorname{tr}(A)
\]

**2. Product of eigenvalues**

The product of eigenvalues, counting algebraic multiplicity, equals the determinant.

\[
\prod \lambda_i = \det(A)
\]

**3. Eigenvalues of a diagonal matrix**

The diagonal entries of a diagonal matrix are its eigenvalues.

**4. Eigenvalues of an identity matrix**

All eigenvalues of the identity matrix are 1.

**5. Eigenvalues of a real symmetric matrix**

All eigenvalues of a real symmetric matrix are real.

## 9. Applications in Machine Learning

### A. Principal Component Analysis (PCA)

PCA is a dimensionality reduction technique that uses eigenvalues and eigenvectors of a covariance matrix.

- Eigenvectors represent principal directions.
- Eigenvalues represent the variance along those directions.
- Directions with larger eigenvalues contain more variance.

PCA uses these directions to represent data with fewer dimensions while retaining as much variance as possible.

### B. Dimensionality Reduction

Eigenvalues help identify which directions contain significant information.

Smaller eigenvalues may correspond to directions with less variance, which can sometimes be excluded when reducing dimensions.

### C. Spectral Clustering

Eigenvectors of graph-related matrices are used to identify structures and clusters in data.

### D. Stability Analysis

Eigenvalues can help analyze the behavior and stability of mathematical and computational systems.

## 10. Applications in Quantum Computing

Eigenvalues and eigenvectors are fundamental to quantum mechanics and quantum computing.

### A. Quantum Observables

Quantum observables are represented by Hermitian operators.

Their eigenvalues correspond to possible measurement outcomes, and their eigenvectors represent the associated eigenstates.

### B. Quantum Gates

Quantum gates are represented by unitary matrices.

Studying their eigenvalues and eigenvectors helps understand their mathematical behavior and transformations.

### C. Quantum Measurement

Measurement can be described using eigenstates of the corresponding observable.

## 11. Python Implementation Using NumPy

NumPy provides the `np.linalg.eig()` function to calculate eigenvalues and eigenvectors.

```python
import numpy as np

# Define a square matrix
A = np.array([
    [4, 1],
    [2, 3]
])

# Calculate eigenvalues and eigenvectors
eigenvalues, eigenvectors = np.linalg.eig(A)

print("Matrix:")
print(A)

print("\nEigenvalues:")
print(eigenvalues)

print("\nEigenvectors:")
print(eigenvectors)

# Verify the eigenvalue equation
for i in range(len(eigenvalues)):
    v = eigenvectors[:, i]
    lam = eigenvalues[i]

    print(f"\nVerification for eigenvalue {lam}:")
    print("Av =", A @ v)
    print("lambda * v =", lam * v)
```

### Expected Eigenvalues

```text
[5. 2.]
```

The eigenvectors returned by NumPy may be normalized, so they can look different from the manually calculated eigenvectors. Both are valid if they satisfy the eigenvalue equation.

## 12. Key Takeaways

- Eigenvectors are special non-zero vectors whose direction remains unchanged under a matrix transformation, up to a possible reversal.
- Eigenvalues describe the scaling factor associated with an eigenvector.
- The characteristic equation is used to calculate eigenvalues.
- Eigenvectors are calculated by solving the corresponding homogeneous system.
- PCA uses eigenvalues and eigenvectors for dimensionality reduction.
- Hermitian matrices in quantum computing have real eigenvalues.

---

**Next Topic:** Matrix Diagonalization and Its Applications in Machine Learning.
