
# Gauss-Seidel Method

## 1. Introduction

The **Gauss-Seidel Method** is an iterative numerical method used to solve a system of linear equations.

Instead of solving all equations directly, it starts with an initial guess and repeatedly improves the values of the unknown variables until the solution becomes sufficiently accurate.

It is particularly useful for solving large systems of linear equations where direct methods may be computationally expensive.

For example, consider:

\[
\begin{aligned}
10x+y+z &= 12\\
2x+10y+z &= 13\\
2x+2y+10z &= 14
\end{aligned}
\]

The exact solution is:

\[
x=1,\quad y=1,\quad z=1
\]

The Gauss-Seidel method approaches this solution through repeated calculations.

---

## 2. Learning Objectives

After studying this topic, you should be able to:

- Understand the Gauss-Seidel iterative method.
- Derive the iteration formula.
- Solve linear equations step by step.
- Understand the convergence conditions.
- Implement the method using Python.
- Compare Gauss-Seidel with the Jacobi method.
- Identify real-world applications and limitations.

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

For a system of three equations:

\[
\begin{aligned}
a_{11}x+a_{12}y+a_{13}z &= b_1\\
a_{21}x+a_{22}y+a_{23}z &= b_2\\
a_{31}x+a_{32}y+a_{33}z &= b_3
\end{aligned}
\]

Rearranging each equation:

\[
x=\frac{b_1-a_{12}y-a_{13}z}{a_{11}}
\]

\[
y=\frac{b_2-a_{21}x-a_{23}z}{a_{22}}
\]

\[
z=\frac{b_3-a_{31}x-a_{32}y}{a_{33}}
\]

These equations are used repeatedly to calculate improved values of the unknowns.

---

## 4. Main Idea of the Gauss-Seidel Method

The most important feature of the Gauss-Seidel method is:

**It immediately uses newly calculated values during the same iteration.**

For example, when calculating:

1. Calculate the new value of \(x\).
2. Use this newly calculated \(x\) to calculate the new value of \(y\).
3. Use the newly calculated \(x\) and \(y\) to calculate the new value of \(z\).

This is different from the Jacobi method, which uses only values from the previous iteration.

---

## 5. General Iteration Formula

For a system of \(n\) linear equations:

\[
AX=B
\]

The Gauss-Seidel iteration formula is:

\[
\boxed{
x_i^{(k+1)}
=
\frac{1}{a_{ii}}
\left[
b_i-
\sum_{j=1}^{i-1}a_{ij}x_j^{(k+1)}
-
\sum_{j=i+1}^{n}a_{ij}x_j^{(k)}
\right]
}
\]

Where:

- \(x_i^{(k+1)}\) = newly calculated value.
- \(x_j^{(k+1)}\) = values already updated in the current iteration.
- \(x_j^{(k)}\) = values from the previous iteration.
- \(a_{ij}\) = coefficient of the variable.
- \(b_i\) = constant term.
- \(k\) = iteration number.

The formula uses updated values wherever they are already available.

---

## 6. Step-by-Step Numerical Example

Solve the following system using the Gauss-Seidel method:

\[
\begin{aligned}
10x+y+z &= 12 \qquad (1)\\
2x+10y+z &= 13 \qquad (2)\\
2x+2y+10z &= 14 \qquad (3)
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

Assume:

\[
x_0=0,\quad y_0=0,\quad z_0=0
\]

These are the initial guesses.

### Step 3: First iteration

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

Use the newly calculated value \(x_1=1.2\).

\[
y_1=\frac{13-2x_1-z_0}{10}
\]

\[
y_1=\frac{13-2(1.2)-0}{10}
\]

\[
\boxed{y_1=1.06}
\]

**Calculate \(z_1\):**

Use the newly calculated values \(x_1=1.2\) and \(y_1=1.06\).

\[
z_1=\frac{14-2x_1-2y_1}{10}
\]

\[
z_1=\frac{14-2(1.2)-2(1.06)}{10}
\]

\[
\boxed{z_1=0.948}
\]

Therefore, after the first iteration:

\[
\boxed{(x_1,y_1,z_1)=(1.2,1.06,0.948)}
\]

### Step 4: Second iteration

Use the values obtained in the first iteration.

**Calculate \(x_2\):**

\[
x_2=\frac{12-y_1-z_1}{10}
\]

\[
x_2=\frac{12-1.06-0.948}{10}
\]

\[
\boxed{x_2=0.9992}
\]

**Calculate \(y_2\):**

Use the newly calculated \(x_2\), but use the previous \(z_1\).

\[
y_2=\frac{13-2x_2-z_1}{10}
\]

\[
y_2=\frac{13-2(0.9992)-0.948}{10}
\]

\[
\boxed{y_2=1.00536}
\]

**Calculate \(z_2\):**

Use the newly calculated \(x_2\) and \(y_2\).

\[
z_2=\frac{14-2x_2-2y_2}{10}
\]

\[
z_2=\frac{14-2(0.9992)-2(1.00536)}{10}
\]

\[
\boxed{z_2=0.999088}
\]

Therefore:

\[
\boxed{
(x_2,y_2,z_2)
=
(0.9992,1.00536,0.999088)
}
\]

These values are already very close to the exact solution:

\[
x=1,\quad y=1,\quad z=1
\]

### Step 5: Continue until convergence

Repeat the same calculations until the difference between consecutive iterations becomes smaller than the chosen tolerance.

For example:

\[
\max |X^{(k+1)}-X^{(k)}|<10^{-6}
\]

When this condition is satisfied, the method stops.

---

## 7. Convergence of the Gauss-Seidel Method

Convergence means that the calculated values gradually approach the actual solution.

The Gauss-Seidel method does not converge for every possible system of linear equations.

### Strict diagonal dominance

A commonly used sufficient condition for convergence is strict diagonal dominance.

A matrix is strictly diagonally dominant if, for every row:

\[
|a_{ii}|>\sum_{j\neq i}|a_{ij}|
\]

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

Check each row:

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

Therefore, the matrix is strictly diagonally dominant, so Gauss-Seidel is guaranteed to converge for this system.

### Other convergence conditions

- A symmetric positive definite coefficient matrix is another sufficient condition for convergence.
- More generally, convergence for every initial guess is guaranteed when the spectral radius of the Gauss-Seidel iteration matrix is less than 1.

Strict diagonal dominance is sufficient, but it is not necessary. Some systems that do not satisfy this condition can still converge.

---

## 8. Python Implementation

We can implement the Gauss-Seidel method using Python and NumPy.

### Code

```python
import numpy as np

def gauss_seidel(A, b, x, tolerance=1e-6, max_iterations=100):
    n = len(b)

    if A.shape != (n, n):
        raise ValueError("A must be a square matrix")

    if np.any(np.diag(A) == 0):
        raise ValueError("Diagonal elements must be non-zero")

    x = np.array(x, dtype=float)

    for iteration in range(max_iterations):
        old_x = x.copy()

        for i in range(n):
            sum_value = 0

            for j in range(n):
                if i != j:
                    sum_value += A[i][j] * x[j]

            x[i] = (b[i] - sum_value) / A[i][i]

        error = np.max(np.abs(x - old_x))

        print(f"Iteration {iteration + 1}: {x}")

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

solution = gauss_seidel(A, b, initial_guess)

print("Final Solution:", solution)
```

### Output

```text
Iteration 1: [1.2   1.06  0.948]
Iteration 2: [0.9992   1.00536  0.999088]
...
Converged!

Final Solution: [1. 1. 1.]
```

The exact number of iterations printed depends on the tolerance and stopping condition.

### Understanding the code

- `A` stores the coefficient matrix.
- `b` stores the constant values.
- `x` stores the initial guesses.
- `old_x` saves the values before the current iteration.
- The inner loop calculates each variable using the latest available values.
- `error` calculates the maximum change between iterations.
- The algorithm stops when the error becomes smaller than the tolerance.

**Important:** The statement `x[i] = ...` updates the solution immediately. This is what makes the implementation Gauss-Seidel rather than Jacobi.

---

## 9. Advantages of the Gauss-Seidel Method

1. Simple and easy to implement.
2. Requires less memory than many direct methods.
3. Often converges faster than the Jacobi method.
4. Suitable for large and sparse systems.
5. Uses newly calculated values immediately, improving the iteration process.

## 10. Disadvantages of the Gauss-Seidel Method

1. Does not converge for every system.
2. Convergence depends on the coefficient matrix.
3. The result is an approximate solution.
4. The variables must be calculated sequentially.
5. It is less suitable for parallel computation because each update depends on earlier updates in the same iteration.

---

## 11. Applications

The Gauss-Seidel method is used in several engineering and scientific fields.

### Electrical Engineering

Used to solve equations in electrical circuits and power-system analysis.

### Computational Fluid Dynamics

Used in numerical simulations involving fluid flow and pressure calculations.

### Heat Transfer

Used to solve temperature distribution equations in physical systems.

### Structural Engineering

Used in numerical analysis of structures and mechanical systems.

### Scientific Computing

Used for solving large sparse systems of linear equations.

---

## 12. Gauss-Seidel vs Jacobi Method

| Feature | Jacobi Method | Gauss-Seidel Method |
|---|---|---|
| Type | Iterative | Iterative |
| Initial guess | Required | Required |
| Updated values | Uses previous iteration values | Uses newly updated values immediately |
| Calculation | All variables use old values | Variables are updated sequentially |
| Convergence | Depends on the system | Depends on the system |
| Speed | Often slower | Often faster |
| Parallel execution | Easier | More difficult |
| Memory | Stores old and new values | Can update values in place |

### Important difference

**Jacobi Method:**

All variables are calculated using values from the previous iteration.

**Gauss-Seidel Method:**

Each newly calculated variable is immediately used to calculate the next variable in the same iteration.

---

## 13. Practice Problems

### Problem 1

Solve using the Gauss-Seidel method:

\[
\begin{aligned}
10x+y+z &= 12\\
2x+10y+z &= 13\\
2x+2y+10z &= 14
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

Explain why strict diagonal dominance is a sufficient condition for convergence of the Gauss-Seidel method.

### Problem 3

Write a Python program to solve a system of linear equations using the Gauss-Seidel method.

### Problem 4

Differentiate between the Jacobi and Gauss-Seidel methods with a suitable example.

### Problem 5

What happens if the coefficient matrix is not diagonally dominant? Does the Gauss-Seidel method always fail?

---

## 14. Conclusion

The Gauss-Seidel method is an iterative numerical technique for solving systems of linear equations.

It starts with initial guesses and repeatedly updates the unknown variables using the latest available values.

Its main advantage over the Jacobi method is that newly calculated values are immediately used in subsequent calculations within the same iteration.

It is particularly useful for large and sparse systems, provided the method converges.

---

## 15. References

- Numerical Methods textbooks.
- NumPy Documentation: https://numpy.org/doc/
- SciPy Documentation: https://docs.scipy.org/doc/scipy/
- Numerical analysis lecture notes.
