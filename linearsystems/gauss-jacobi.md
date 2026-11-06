
# Gauss-Jacobi Method

## 1. Introduction

The **Gauss-Jacobi Method**, also known as the **Jacobi Iterative Method**, is an iterative numerical technique used to solve a system of linear equations.

Instead of solving all equations directly, it starts with an initial guess for the unknown variables and repeatedly calculates improved values until the solution becomes sufficiently accurate.

It is particularly useful for solving large systems of linear equations.

Consider the system:

\[
\begin{aligned}
10x+y+z&=12\\
2x+10y+z&=13\\
2x+2y+10z&=14
\end{aligned}
\]

The exact solution is:

\[
x=1,\quad y=1,\quad z=1
\]

The Jacobi method approaches this solution through repeated iterations.

---

## 2. Learning Objectives

After studying this topic, you should be able to:

- Understand the Gauss-Jacobi iterative method.
- Derive the iteration formula.
- Solve linear equations step by step.
- Understand convergence conditions.
- Implement the method using Python.
- Differentiate Jacobi and Gauss-Seidel methods.

---

## 3. Mathematical Foundation

A system of linear equations can be represented in matrix form:

\[
AX=B
\]

Where:

- \(A\) is the coefficient matrix.
- \(X\) is the vector of unknown variables.
- \(B\) is the constant vector.

For three variables:

\[
\begin{aligned}
a_{11}x+a_{12}y+a_{13}z&=b_1\\
a_{21}x+a_{22}y+a_{23}z&=b_2\\
a_{31}x+a_{32}y+a_{33}z&=b_3
\end{aligned}
\]

The first step is to rearrange each equation to isolate one variable.

\[
x=\frac{b_1-a_{12}y-a_{13}z}{a_{11}}
\]

\[
y=\frac{b_2-a_{21}x-a_{23}z}{a_{22}}
\]

\[
z=\frac{b_3-a_{31}x-a_{32}y}{a_{33}}
\]

These rearranged equations are used to calculate new approximations.

---

## 4. Main Idea of the Gauss-Jacobi Method

The most important rule of the Jacobi method is:

**Every variable in a new iteration must be calculated using only the values from the previous iteration.**

For example:

1. Calculate the new value of \(x\) using old values of \(y\) and \(z\).
2. Calculate the new value of \(y\) using old values of \(x\) and \(z\).
3. Calculate the new value of \(z\) using old values of \(x\) and \(y\).

Even if the new value of \(x\) has already been calculated, it must not be used to calculate the new value of \(y\) in the same iteration.

All variables are updated together after the calculations are completed.

---

## 5. General Iteration Formula

For a system of \(n\) linear equations:

\[
AX=B
\]

The Jacobi iteration formula is:

\[
\boxed{
x_i^{(k+1)}
=
\frac{1}{a_{ii}}
\left(
b_i-\sum_{j\neq i}a_{ij}x_j^{(k)}
\right)
}
\]

Where:

- \(x_i^{(k+1)}\) = new value of the variable.
- \(x_j^{(k)}\) = previous iteration value.
- \(a_{ij}\) = coefficient of the variable.
- \(a_{ii}\) = diagonal coefficient.
- \(b_i\) = constant term.
- \(k\) = iteration number.

Notice that every variable on the right-hand side has iteration number \(k\).

This means only old values are used.

---

## 6. Step-by-Step Numerical Example

Solve the following system using the Gauss-Jacobi method:

\[
\begin{aligned}
10x+y+z&=12 \qquad (1)\\
2x+10y+z&=13 \qquad (2)\\
2x+2y+10z&=14 \qquad (3)
\end{aligned}
\]

### Step 1: Rearrange the equations

From equation (1):

\[
x=\frac{12-y-z}{10}
\]

From equation (2):

\[
y=\frac{13-2x-z}{10}
\]

From equation (3):

\[
z=\frac{14-2x-2y}{10}
\]

### Step 2: Choose initial values

Assume all initial values are zero:

\[
x_0=0,\quad y_0=0,\quad z_0=0
\]

### Step 3: First iteration

Calculate all new values using the initial values.

**Calculate \(x_1\):**

\[
x_1=\frac{12-y_0-z_0}{10}
\]

\[
x_1=\frac{12-0-0}{10}
\]

\[
\boxed{x_1=1.2}
\]

**Calculate \(y_1\):**

\[
y_1=\frac{13-2x_0-z_0}{10}
\]

\[
y_1=\frac{13-2(0)-0}{10}
\]

\[
\boxed{y_1=1.3}
\]

**Calculate \(z_1\):**

\[
z_1=\frac{14-2x_0-2y_0}{10}
\]

\[
z_1=\frac{14-2(0)-2(0)}{10}
\]

\[
\boxed{z_1=1.4}
\]

Therefore, after the first iteration:

\[
\boxed{(x_1,y_1,z_1)=(1.2,1.3,1.4)}
\]

### Step 4: Second iteration

Now use only the values from the first iteration.

**Calculate \(x_2\):**

\[
x_2=\frac{12-y_1-z_1}{10}
\]

\[
x_2=\frac{12-1.3-1.4}{10}
\]

\[
\boxed{x_2=0.93}
\]

**Calculate \(y_2\):**

\[
y_2=\frac{13-2x_1-z_1}{10}
\]

\[
y_2=\frac{13-2(1.2)-1.4}{10}
\]

\[
\boxed{y_2=0.92}
\]

**Calculate \(z_2\):**

\[
z_2=\frac{14-2x_1-2y_1}{10}
\]

\[
z_2=\frac{14-2(1.2)-2(1.3)}{10}
\]

\[
\boxed{z_2=0.90}
\]

Therefore:

\[
\boxed{(x_2,y_2,z_2)=(0.93,0.92,0.90)}
\]

### Step 5: Third iteration

Use the values from the second iteration.

**Calculate \(x_3\):**

\[
x_3=\frac{12-0.92-0.90}{10}
\]

\[
\boxed{x_3=1.018}
\]

**Calculate \(y_3\):**

\[
y_3=\frac{13-2(0.93)-0.90}{10}
\]

\[
\boxed{y_3=1.024}
\]

**Calculate \(z_3\):**

\[
z_3=\frac{14-2(0.93)-2(0.92)}{10}
\]

\[
\boxed{z_3=1.03}
\]

Therefore:

\[
\boxed{(x_3,y_3,z_3)=(1.018,1.024,1.03)}
\]

### Step 6: Continue until convergence

Repeat the calculations until the difference between consecutive iterations becomes sufficiently small.

The values gradually approach:

\[
\boxed{x=1,\quad y=1,\quad z=1}
\]

---

## 7. Iteration Table

The first three iterations are summarized below.

| Iteration | x | y | z |
|---|---:|---:|---:|
| Initial | 0 | 0 | 0 |
| 1 | 1.200 | 1.300 | 1.400 |
| 2 | 0.930 | 0.920 | 0.900 |
| 3 | 1.018 | 1.024 | 1.030 |
| 4 | 0.9946 | 0.9934 | 0.9916 |

The values move closer to the exact solution with each iteration.

---

## 8. Convergence of the Gauss-Jacobi Method

Convergence means that the calculated values gradually approach the actual solution.

The Jacobi method does not converge for every system of linear equations.

### Strict Diagonal Dominance

A commonly used sufficient condition for convergence is strict diagonal dominance.

A matrix is strictly diagonally dominant if:

\[
\boxed{
|a_{ii}|>\sum_{j\neq i}|a_{ij}|
}
\]

for every row.

In simple words:

The absolute value of the diagonal element must be greater than the sum of the absolute values of all other elements in that row.

Consider:

\[
A=
\begin{bmatrix}
10&1&1\\
2&10&1\\
2&2&10
\end{bmatrix}
\]

Check each row.

**Row 1:**

\[
10>|1|+|1|=2
\]

**Row 2:**

\[
10>|2|+|1|=3
\]

**Row 3:**

\[
10>|2|+|2|=4
\]

Therefore, the matrix is strictly diagonally dominant, and the Jacobi method is guaranteed to converge.

### Other Convergence Condition

The more general convergence condition is:

\[
\boxed{\rho(T_J)<1}
\]

Where:

- \(T_J\) is the Jacobi iteration matrix.
- \(\rho(T_J)\) is its spectral radius, the largest absolute value of its eigenvalues.

Strict diagonal dominance is sufficient but not necessary for convergence.

---

## 9. Stopping Condition

The iterations should stop when the difference between consecutive approximations becomes smaller than a specified tolerance.

A common stopping condition is:

\[
\boxed{
\max_i|x_i^{(k+1)}-x_i^{(k)}|<\epsilon
}
\]

Where:

- \(\epsilon\) = tolerance.
- \(k\) = iteration number.

For example:

\[
\epsilon=10^{-6}
\]

This means the maximum change in any variable must be less than 0.000001.

---

## 10. Python Implementation Using NumPy

### Code

```python
import numpy as np

def gauss_jacobi(A, b, x, tolerance=1e-6, max_iterations=100):
    n = len(b)

    if A.shape != (n, n):
        raise ValueError("A must be a square matrix")

    if np.any(np.diag(A) == 0):
        raise ValueError("Diagonal elements must be non-zero")

    x = np.array(x, dtype=float)

    for iteration in range(max_iterations):

        # Store new values separately
        x_new = np.zeros(n)

        for i in range(n):
            sum_value = 0

            for j in range(n):
                if i != j:
                    sum_value += A[i][j] * x[j]

            x_new[i] = (b[i] - sum_value) / A[i][i]

        error = np.max(np.abs(x_new - x))

        print(f"Iteration {iteration + 1}: {x_new}")

        # Update all variables together
        x = x_new

        if error < tolerance:
            print("Converged!")
            return x

    print("Maximum iterations reached.")
    return x


A = np.array([
    [10, 1, 1],
    [2, 10, 1],
    [2, 2, 10]
], dtype=float)

b = np.array([12, 13, 14], dtype=float)

initial_guess = [0, 0, 0]

solution = gauss_jacobi(A, b, initial_guess)

print("Final Solution:", solution)
```

### Output

```text
Iteration 1: [1.2 1.3 1.4]
Iteration 2: [0.93 0.92 0.9]
Iteration 3: [1.018 1.024 1.03]
...
Converged!

Final Solution: [1. 1. 1.]
```

The exact number of iterations depends on the tolerance.

### Understanding the Code

| Code | Purpose |
|---|---|
| `A` | Stores the coefficient matrix |
| `b` | Stores the constant values |
| `x` | Stores previous iteration values |
| `x_new` | Stores newly calculated values |
| `sum_value` | Calculates the contribution of other variables |
| `error` | Measures the maximum change |
| `tolerance` | Defines the required accuracy |
| `max_iterations` | Limits the number of iterations |

**Important:** The use of `x_new` is essential. Every calculation reads from the old array `x`, and only after all variables are calculated do we update `x`.

---

## 11. Advantages

1. Simple and easy to understand.
2. Easy to implement using programming languages.
3. Suitable for large systems of linear equations.
4. Requires relatively little memory.
5. Calculations for each variable in an iteration can be performed in parallel.
6. Useful for sparse matrices.

## 12. Disadvantages

1. Does not converge for every system.
2. May require many iterations.
3. Convergence depends on the coefficient matrix.
4. Can be slower than the Gauss-Seidel method.
5. Requires a suitable stopping condition.
6. The initial guess can affect the convergence process.

---

## 13. Applications

### Engineering

Used to solve systems of equations in electrical and mechanical engineering.

### Heat Transfer

Used in numerical calculations involving temperature distribution.

### Computational Fluid Dynamics

Used in numerical simulations of fluid flow.

### Scientific Computing

Used to solve large systems of linear equations.

### Numerical Analysis

Used as a basic iterative technique for studying convergence and approximation.

---

## 14. Gauss-Jacobi vs Gauss-Seidel Method

| Feature | Gauss-Jacobi | Gauss-Seidel |
|---|---|---|
| Type | Iterative | Iterative |
| Initial guess | Required | Required |
| Updated values | Uses only previous iteration values | Uses newly calculated values immediately |
| Calculation | All variables calculated independently | Variables calculated sequentially |
| Memory | Stores old and new values | Can update values in place |
| Parallelization | Easier | More difficult |
| Convergence | Depends on the system | Depends on the system |
| Speed | Often slower | Often faster |

### Important Difference

**Gauss-Jacobi:**

Every new variable is calculated using values from the previous iteration.

**Gauss-Seidel:**

Newly calculated values are immediately used to calculate the remaining variables in the same iteration.

---

## 15. Practice Problems

### Problem 1

Solve using the Gauss-Jacobi method:

\[
\begin{aligned}
10x+y+z&=12\\
2x+10y+z&=13\\
2x+2y+10z&=14
\end{aligned}
\]

Use the initial guess:

\[
x_0=y_0=z_0=0
\]

Expected solution:

\[
x=1,\quad y=1,\quad z=1
\]

### Problem 2

Check whether the following matrix is strictly diagonally dominant:

\[
A=
\begin{bmatrix}
8&1&1\\
2&9&1\\
1&2&7
\end{bmatrix}
\]

### Problem 3

Explain why the Jacobi method uses previous iteration values.

### Problem 4

Write a Python program to solve a system using the Gauss-Jacobi method.

### Problem 5

Differentiate between the Gauss-Jacobi and Gauss-Seidel methods.

---

## 16. Conclusion

The Gauss-Jacobi Method is an iterative numerical technique used to solve systems of linear equations.

It begins with an initial guess and repeatedly calculates improved approximations.

Its most important characteristic is that every new variable is calculated using only the values from the previous iteration.

It is useful for large systems, especially when the coefficient matrix satisfies suitable convergence conditions.

---

## 17. References

- Numerical Methods textbooks.
- NumPy Documentation: https://numpy.org/doc/
- SciPy Documentation: https://docs.scipy.org/doc/scipy/
- Numerical Analysis lecture notes.
