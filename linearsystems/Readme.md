# Linear Systems

This section covers different mathematical and computational techniques for solving systems of linear equations. Each notebook combines mathematical theory, step-by-step derivations, numerical examples, Python implementations, visualizations, and real-world applications in Machine Learning and Scientific Computing.

## 📚 Topics Covered

### 1. Gaussian Elimination
**File:** `gaussian-elimination.ipynb`

- Introduction to systems of linear equations
- Augmented matrix representation
- Elementary row operations
- Forward elimination and back substitution
- Pivot elements and partial pivoting
- Solving 2×2 and 3×3 systems
- Python implementation using NumPy
- Comparison with `numpy.linalg.solve()`
- Applications in Machine Learning

### 2. Gauss-Jordan Elimination
**File:** `gauss-jordan-elimination.ipynb`

- Introduction to Gauss-Jordan elimination
- Gaussian vs. Gauss-Jordan elimination
- Reduced Row Echelon Form (RREF)
- Conditions for RREF
- Elementary row operations
- Step-by-step matrix transformations
- Unique, infinite, and inconsistent solutions
- Python implementation using NumPy and SymPy
- Matrix inverse calculation
- Practical applications

### 3. LU Decomposition
**File:** `lu-decomposition.ipynb`

- Introduction to matrix factorization
- Lower triangular and upper triangular matrices
- LU decomposition: A = LU
- Doolittle's method
- Crout's method
- Step-by-step numerical examples
- Forward and backward substitution
- Python implementation using NumPy and SciPy
- Verification of matrix factorization
- Applications in numerical computing and Machine Learning

### 4. Cramer's Rule
**File:** `cramers-rule.ipynb`

- Introduction to Cramer's Rule
- Determinants and their properties
- Conditions for applying Cramer's Rule
- Determinants of 2×2 and 3×3 matrices
- Mathematical derivation
- Column replacement technique
- Step-by-step numerical examples
- Python implementation using NumPy
- Singular matrices and zero determinants
- Advantages and limitations

### 5. Jacobi Iterative Method
**File:** `jacobi-method.ipynb`

- Introduction to iterative numerical methods
- Direct vs. iterative methods
- Derivation of Jacobi iteration formula
- Diagonal dominance
- Initial approximation
- Step-by-step iteration process
- Convergence conditions
- Error calculation and tolerance
- Python implementation from scratch
- Convergence visualization
- Applications in large-scale numerical systems

### 6. Gauss-Seidel Method
**File:** `gauss-seidel-method.ipynb`

- Introduction to the Gauss-Seidel method
- Mathematical derivation
- Iterative formula
- Difference between Jacobi and Gauss-Seidel methods
- Use of updated values during iterations
- Convergence conditions
- Step-by-step numerical examples
- Error calculation and stopping criteria
- Python implementation
- Convergence graphs
- Performance comparison with Jacobi method

### 7. Matrix Inverse Method
**File:** `matrix-inverse-method.ipynb`

- Introduction to inverse matrices
- Conditions for matrix invertibility
- Singular and non-singular matrices
- Properties of inverse matrices
- Finding inverse using Gauss-Jordan elimination
- Inverse of 2×2 and 3×3 matrices
- Solving AX = B using X = A⁻¹B
- Step-by-step numerical examples
- Python implementation using NumPy
- Verification using AA⁻¹ = I
- Applications in Machine Learning
- Limitations of inverse-based solutions

---

## 🛠️ Technologies and Libraries

- Python
- Jupyter Notebook
- NumPy
- SciPy
- SymPy
- Matplotlib
- Seaborn

## 📖 Learning Structure

Each notebook follows a consistent learning structure:

1. Introduction and learning objectives
2. Mathematical foundations and theory
3. Important formulas and derivations
4. Step-by-step numerical examples
5. Python implementation from scratch
6. Execution and output verification
7. Graphical visualizations
8. Real-world applications
9. Advantages and limitations
10. Practice problems with solutions
11. Summary and conclusion

## 🎯 Learning Objectives

By completing these notebooks, learners will be able to:

- Understand different methods of solving linear systems.
- Perform elementary row operations and matrix transformations.
- Apply direct and iterative numerical methods.
- Understand matrix decomposition techniques.
- Implement mathematical algorithms using Python.
- Analyze convergence and numerical accuracy.
- Apply linear algebra concepts to Machine Learning and scientific computing.

## 🌍 Applications

Linear systems are fundamental to several areas of computing and engineering, including:

- Machine Learning model optimization
- Linear regression
- Numerical simulations
- Computer graphics
- Engineering problem-solving
- Scientific computing
- Quantum computing and mathematical modelling

---

**Goal:** Build a strong mathematical and computational understanding of linear systems through theory, numerical problem-solving, and practical Python implementations.
