# Linear Independence and Dependence

## 1. Introduction

Linear independence is a fundamental concept in linear algebra. It determines whether a set of vectors contains unique directions or whether some vectors can be represented using combinations of the others.

A set of vectors is either linearly independent or linearly dependent.

## 2. Linear Independence

A set of vectors is linearly independent if the only solution to the equation

\[
c_1v_1+c_2v_2+\cdots+c_nv_n=0
\]

is:

\[
c_1=c_2=\cdots=c_n=0
\]

This means no vector in the set can be expressed as a linear combination of the remaining vectors.

### Example

Consider:

\[
v_1=[1,0],\quad v_2=[0,1]
\]

Suppose:

\[
c_1[1,0]+c_2[0,1]=[0,0]
\]

This gives:

\[
c_1=0,\quad c_2=0
\]

Therefore, the vectors are linearly independent.

## 3. Linear Dependence

A set of vectors is linearly dependent if there exists a non-zero solution to:

\[
c_1v_1+c_2v_2+\cdots+c_nv_n=0
\]

This means at least one vector can be represented using the other vectors.

### Example

Consider:

\[
v_1=[1,2],\quad v_2=[2,4]
\]

Notice:

\[
v_2=2v_1
\]

Therefore, the vectors are linearly dependent.

## 4. Testing Linear Independence Using Matrices

Place the vectors as columns of a matrix.

For a square matrix, the vectors are linearly independent if:

\[
\det(A)\neq0
\]

For matrices of any shape, the columns are linearly independent if the matrix has full column rank.

## 5. Python Implementation Using NumPy

```python
import numpy as np

# Linearly independent vectors
A = np.array([
    [1, 0],
    [0, 1]
])

rank_A = np.linalg.matrix_rank(A)

print("Rank:", rank_A)
print("Independent:", rank_A == A.shape[1])
```

### Dependent Vectors

```python
B = np.array([
    [1, 2],
    [2, 4]
])

rank_B = np.linalg.matrix_rank(B)

print("Rank:", rank_B)
print("Independent:", rank_B == B.shape[1])
```

## 6. Applications

### Machine Learning
- Identifying redundant features.
- Detecting multicollinearity.
- Understanding feature spaces.

### Data Science
- Removing duplicate information.
- Analyzing relationships between variables.

### Computer Graphics
- Representing independent directions in coordinate systems.

### Quantum Computing
- Understanding orthogonal and independent quantum state vectors.

## 7. Conclusion

Linear independence determines whether vectors contain unique information. Linear dependence indicates redundancy because one or more vectors can be represented using the others.

This concept is essential for understanding basis, dimension, matrix rank, and vector spaces.

## References
- NumPy: https://numpy.org/doc/stable/reference/generated/numpy.linalg.matrix_rank.html
