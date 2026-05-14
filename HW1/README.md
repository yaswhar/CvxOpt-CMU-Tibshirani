# Homework 1 – Convex Sets, Functions & SVM

**Course:** Convex Optimization (10-725) – CMU Fall 2019  
**Points:** 66 (+ 10 bonus)

---

## Contents

| File | Description |
|------|-------------|
| `CvxOpt_HW1_404210253.pdf` | Full written solution (typeset in LaTeX) – proofs and derivations for all problems |
| `HW1 - Solution - Code.ipynb` | Jupyter notebook implementing the SVM problem with CVXPY |
| `svm_decision_boundary.png` | Plot of training data and the SVM decision boundary ($C=1$) |
| `svm_error_vs_C.png` | Misclassification error on test data as a function of the regularisation parameter $C$ |
| `xy_train.csv` | Training data (2 features, binary labels) |
| `xy_test.csv` | Test data (2 features, binary labels) |

---

## Problem Summary

### 1. Convex Sets (16 points)

- Prove that polyhedra $\{x : Ax \le b\}$ are both convex and closed.
- Show that intersections of convex (or closed) sets remain convex (closed).
- Provide a closed set in $\mathbb{R}^2$ whose convex hull is not closed.
- Prove that preimages $A^{-1}(S)$ and images $A(S)$ of convex sets under linear maps are convex (and similarly for closed sets, with a counterexample for images).
- Show that images and preimages of polyhedra under linear maps are polyhedra.

### 2. Convex Functions (14 points)

- Prove that the entropy function $f(x) = -\sum_{i=1}^n x_i \log x_i$ is strictly concave on the probability simplex.
- Prove that for a twice‑differentiable $f$, convexity is equivalent to monotonicity of the gradient: $(\nabla f(x) - \nabla f(y))^T(x-y) \ge 0$.
- Give an example of a strictly convex function that does not attain its infimum.
- Prove properties of coercive functions and the existence of global minimisers.

### 3. Support Vector Machine (22 points)

- **(i)** Formulate and solve the soft‑margin SVM primal problem with $C=1$ using CVXPY. Report the optimal objective value and coefficients $\beta, \beta_0$.
- **(ii)** Plot the training data and the decision boundary $\beta_0 + \beta^T x = 0$.
- **(iii)** Reformulate the SVM as a quadratic program in terms of $\tilde{X} = y_i x_i$, solve with CVX, and verify that the solutions match part (i).
- **(iv)** Vary $C$ over a logarithmic range, solve the SVM for each, and plot the test misclassification error versus $C$.

### 4. Disciplined Convex Programming (14 pts + 10 bonus)

- Analyse whether given functions/expressions are convex, concave, both, or neither, using DCP rules.
- Determine whether a given optimisation problem is convex, and if so, rewrite it in a DCP‑compliant form compatible with CVX.

---

## Results

### SVM Decision Boundary ($C=1$)

![SVM Decision Boundary](https://github.com/yaswhar/CvxOpt-CMU-Tibshirani/blob/main/HW1/svm_decision_boundary.png)

**Optimal criterion value:** 36.75  
**Optimal coefficients:** $\beta = [1.42, 1.25]$, $\beta_0 = -2.82$

### Misclassification Error vs. $C$

![Error vs C](https://github.com/yaswhar/CvxOpt-CMU-Tibshirani/blob/main/HW1/svm_error_vs_C.png)

The misclassification error on the test set varies with the regularisation parameter $C$. Small $C$ (strong regularisation) leads to underfitting, while large $C$ (weak regularisation) increases variance. The optimal $C$ lies in an intermediate range.

---

## How to Run the Code

1. **Install dependencies:**
   ```bash
   pip install cvxpy numpy matplotlib
   ```

2. **Launch the notebook:**
   ```bash
   jupyter notebook "HW1 - Solution - Code.ipynb"
   ```

3. Ensure `xy_train.csv` and `xy_test.csv` are in the same directory as the notebook.

---

## References

- [Boyd & Vandenberghe, *Convex Optimization* (2004)](https://web.stanford.edu/~boyd/cvxbook/bv_cvxbook.pdf)
- [CVXPY Documentation](https://www.cvxpy.org/)
- [Course Homework Page](https://www.stat.cmu.edu/~ryantibs/convexopt/#homework)
