
# Cramer's Rule

## 1. Introduction

Cramer's Rule is a mathematical method used to solve systems of linear equations using determinants.

It provides a direct formula for calculating the values of unknown variables in a square system of linear equations.

Cramer's Rule is applicable when the determinant of the coefficient matrix is non-zero.

It is particularly useful for understanding the relationship between determinants, matrix invertibility, and solutions of linear systems.

## 2. Learning Objectives

- Understand determinants and their properties.
- Calculate determinants of 2×2 and 3×3 matrices.
- Understand the mathematical foundation of Cramer's Rule.
- Solve systems of linear equations using determinants.
- Implement Cramer's Rule using Python.
- Identify singular and non-singular matrices.
- Understand the advantages and limitations of the method.

## 3. Mathematical Foundation

Consider a system of linear equations represented as:

\[
Ax=b
\]

Where:

- A is the coefficient matrix.
- x is the unknown variable vector.
- b is the constant vector.

According to Cramer's Rule:

\[
x_i=\frac{\det(A_i)}{\det(A)}
\]

Where:

- \(A\) is the original coefficient matrix.
- \(A_i\) is obtained by replacing the ith column of A with the constant vector b.
- \(\det(A)\) is the determinant of the original matrix.

### Important Condition

\[
\det(A)\neq 0
\]

If the determinant is non-zero, the system has a unique solution.

## 4. Understanding Determinants

A determinant is a scalar value calculated from a square matrix.

It provides information about whether a matrix is invertible.

### 4.1 Determinant of a 2×2 Matrix

For:

\[
A=
\begin{bmatrix}
a&b\\
c&d
\end{bmatrix}
\]

The determinant is:

\[
\det(A)=ad-bc
\]

Example:

\[
A=
\begin{bmatrix}
2&3\\
1&-1
\end{bmatrix}
\]

\[
\det(A)=(2)(-1)-(3)(1)
\]

\[
\boxed{\det(A)=-5}
\]

### 4.2 Determinant of a 3×3 Matrix

For:

\[
A=
\begin{bmatrix}
a&b&c\\
d&e&f\\
g&h&i
\end{bmatrix}
\]

The determinant is:

\[
\det(A)=a(ei-fh)-b(di-fg)+c(dh-eg)
\]

This method is called cofactor expansion along the first row.

## 5. Numerical Example: Solving a 2×2 System

Consider:

\[
\begin{aligned}
2x+3y&=8\\
x-y&=1
\end{aligned}
\]

### Step 1: Construct the coefficient matrix

\[
A=
\begin{bmatrix}
2&3\\
1&-1
\end{bmatrix}
\]

The constant vector is:

\[
b=
\begin{bmatrix}
8\\
1
\end{bmatrix}
\]

### Step 2: Calculate the determinant D

\[
D=\det(A)
\]

\[
D=(2)(-1)-(3)(1)
\]

\[
D=-5
\]

Since D is non-zero, the system has a unique solution.

### Step 3: Calculate Dx

Replace the first column of A with b.

\[
A_x=
\begin{bmatrix}
8&3\\
1&-1
\end{bmatrix}
\]

\[
D_x=(8)(-1)-(3)(1)
\]

\[
D_x=-11
\]

### Step 4: Calculate Dy

Replace the second column of A with b.

\[
A_y=
\begin{bmatrix}
2&8\\
1&1
\end{bmatrix}
\]

\[
D_y=(2)(1)-(8)(1)
\]

\[
D_y=-6
\]

### Step 5: Calculate the unknown variables

\[
x=\frac{D_x}{D}
\]

\[
x=\frac{-11}{-5}=\frac{11}{5}
\]

Similarly:

\[
y=\frac{D_y}{D}
\]

\[
y=\frac{-6}{-5}=\frac{6}{5}
\]

Final solution:

\[
\boxed{x=2.2,\quad y=1.2}
\]

## 6. Numerical Example: Solving a 3×3 System

Consider:

\[
\begin{aligned}
x+y+z&=6\\
2x+y-z&=1\\
x-y+2z&=5
\end{aligned}
\]

The coefficient matrix is:

\[
A=
\begin{bmatrix}
1&1&1\\
2&1&-1\\
1&-1&2
\end{bmatrix}
\]

The constant vector is:

\[
b=
\begin{bmatrix}
6\\
1\\
5
\end{bmatrix}
\]

The determinant of A is:

\[
D=
\begin{vmatrix}
1&1&1\\
2&1&-1\\
1&-1&2
\end{vmatrix}
\]

Expanding along the first row:

\[
D=1(2-1)-1(4+1)+1(-2-1)
\]

\[
D=1-5-3=-7
\]

Replacing the first column:

\[
A_x=
\begin{bmatrix}
6&1&1\\
1&1&-1\\
5&-1&2
\end{bmatrix}
\]

\[
D_x=-7
\]

Replacing the second column:

\[
A_y=
\begin{bmatrix}
1&6&1\\
2&1&-1\\
1&5&2
\end{bmatrix}
\]

\[
D_y=-14
\]

Replacing the third column:

\[
A_z=
\begin{bmatrix}
1&1&6\\
2&1&1\\
1&-1&5
\end{bmatrix}
\]

\[
D_z=-21
\]

Therefore:

\[
x=\frac{-7}{-7}=1
\]

\[
y=\frac{-14}{-7}=2
\]

\[
z=\frac{-21}{-7}=3
\]

Final solution:

\[
\boxed{x=1,\quad y=2,\quad z=3}
\]

## 7. Python Implementation

The following implementation solves a system using Cramer's Rule.

```python
import numpy as np

def cramers_rule(A, b):

    A = np.array(A, dtype=float)
    b = np.array(b, dtype=float)

    D = np.linalg.det(A)

    if np.isclose(D, 0):
        raise ValueError(
            "Determinant is zero. "
            "A unique solution does not exist."
        )

    solution = []

    for i in range(len(b)):

        Ai = A.copy()

        # Replace the ith column with b
        Ai[:, i] = b

        Di = np.linalg.det(Ai)

        solution.append(Di / D)

    return np.array(solution)


A = [
    [2, 3],
    [1, -1]
]

b = [8, 1]

solution = cramers_rule(A, b)

print("Solution:", solution)

print("Verification:", np.array(A) @ solution)
```

### Expected Output

```text
Solution: [2.2 1.2]

Verification: [8. 1.]
```

## 8. Special Cases

### 8.1 Non-zero Determinant

If:

\[
\det(A)\neq 0
\]

The system has exactly one solution.

Cramer's Rule can calculate every unknown variable.

### 8.2 Zero Determinant

If:

\[
\det(A)=0
\]

Cramer's Rule cannot provide a unique solution.

The system may have:

- No solution.
- Infinitely many solutions.

Additional analysis is required to distinguish these cases.

## 9. Applications

### Engineering Calculations

Used in small systems of equations involving physical and engineering quantities.

### Mathematical Modelling

Helps calculate unknown variables in mathematical models.

### Linear Algebra

Demonstrates the relationship between determinants and matrix invertibility.

### Theoretical Computer Science

Provides a mathematical foundation for understanding linear systems and matrix operations.

## 10. Advantages

- Simple mathematical formulation.
- Easy to apply to small systems.
- Provides direct expressions for unknown variables.
- Helps understand determinant properties.
- Useful for theoretical analysis.

## 11. Limitations

- Computationally expensive for large systems.
- Requires a non-zero determinant.
- Repeated determinant calculations increase computational cost.
- Not suitable for large-scale numerical systems.
- Floating-point determinant calculations may introduce numerical errors.

For practical large-scale numerical problems, Gaussian Elimination or LU Decomposition is generally preferred.

## 12. Comparison with Gaussian Elimination

| Feature | Cramer's Rule | Gaussian Elimination |
|---|---|---|
| Main concept | Determinants | Row operations |
| Calculation | Repeated determinants | Matrix transformations |
| Large systems | Inefficient | More suitable |
| Unique solution | Requires non-zero determinant | Requires appropriate rank conditions |
| Implementation | Relatively simple for small systems | Requires elimination and substitution |

## 13. Practice Questions

1. Define Cramer's Rule.
2. State the condition required to apply Cramer's Rule.
3. Calculate the determinant of a 2×2 matrix.
4. Solve a 2×2 system using Cramer's Rule.
5. Solve a 3×3 system using Cramer's Rule.
6. What happens when the determinant is zero?
7. Differentiate singular and non-singular matrices.
8. Compare Cramer's Rule with Gaussian Elimination.
9. Why is Cramer's Rule inefficient for large systems?

## 14. Conclusion

Cramer's Rule provides a determinant-based approach to solving systems of linear equations.

It demonstrates the relationship between determinants, matrix invertibility, and unique solutions.

Although it is not computationally efficient for large systems, it remains an important theoretical technique in Linear Algebra.

## References

- Gilbert Strang - Introduction to Linear Algebra.
- [NumPy Documentation](https://numpy.org/doc/)
- [MIT OpenCourseWare - Linear Algebra](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/)
```

**Next file:** `jacobi-method.md`.
