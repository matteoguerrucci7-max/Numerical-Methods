# Numerical-Methods

Personal study notes on numerical analysis, written from scratch in
English, covering chapters 1 through 7 of the course *Metodi Numerici*.
Each topic is presented as **theory first** (definitions and theorems,
with the source they come from) followed by a small, tested Python/NumPy
implementation that verifies or illustrates the result experimentally —
e.g. showing empirically what the machine epsilon is and why it exists, or
checking that the condition number of a matrix really does bound how much
a perturbation of `b` is amplified in the solution `x` of `Ax = b`.

## Contents

The single notebook [`notebooks/L1-L7_numerical_methods.ipynb`](notebooks/L1-L7_numerical_methods.ipynb)
is organized as:

| Section | Topic |
|---|---|
| L1 | Tools of the trade — floating point & machine epsilon, norms, condition number, eigenvalues/eigenvectors, SVD |
| L2 | Linear systems — Gaussian elimination, LU factorization, Jacobi method, gradient (steepest descent) method |
| L3 | Nonlinear equations — Newton's method |
| L4 | Overdetermined systems — normal equations, QR factorization (Gram–Schmidt), least squares |
| L5 | Polynomial approximation — Lagrange interpolation, interpolation error, piecewise linear interpolation |
| L6 | Numerical differentiation and integration — finite differences, Newton–Cotes (trapezoidal, Simpson) |
| L7 | Eigenvalue computation — power method, inverse power method, QR algorithm |

## Diagrams

The [`diagrams/`](diagrams) folder collects standalone HTML reference
sheets that summarize a topic visually, as a complement to the notebook:

| File | Topic | View rendered |
|---|---|---|
| [`L1_tools_of_the_trade.html`](diagrams/L1_tools_of_the_trade.html) | Chapter 1 concept map — floating point, norms, condition number, eigenvalues, SVD | [open](https://htmlpreview.github.io/?https://raw.githubusercontent.com/matteoguerrucci7-max/Numerical-Methods/main/diagrams/L1_tools_of_the_trade.html) |
| [`L2_linear_systems.html`](diagrams/L2_linear_systems.html) | Linear systems — direct methods, iterative methods, gradient-type methods | [open](https://htmlpreview.github.io/?https://raw.githubusercontent.com/matteoguerrucci7-max/Numerical-Methods/main/diagrams/L2_linear_systems.html) |
| [`L3_nonlinear_equations_systems.html`](diagrams/L3_nonlinear_equations_systems.html) | Nonlinear equations and systems — bisection, Newton, secant, fixed-point iteration and their generalization to ℝⁿ | [open](https://htmlpreview.github.io/?https://raw.githubusercontent.com/matteoguerrucci7-max/Numerical-Methods/main/diagrams/L3_nonlinear_equations_systems.html) |
| [`L4_overdetermined_systems.html`](diagrams/L4_overdetermined_systems.html) | Overdetermined systems — normal equations, QR factorization, Gram–Schmidt (classical/modified), Householder reflections | [open](https://htmlpreview.github.io/?https://raw.githubusercontent.com/matteoguerrucci7-max/Numerical-Methods/main/diagrams/L4_overdetermined_systems.html) |

GitHub only shows the raw HTML source when you click a file above —
use the "open" links to see it rendered directly in the browser
(via [htmlpreview.github.io](https://htmlpreview.github.io)).

## Animations — PCA rugby project

The [`download/`](download) folder holds standalone animations of a side
project that applies chapter 1 and 7 tools (covariance, SVD, power method
with deflation) to a synthetic rugby squad of 25 players × 10 statistics:
find the playing-style axes, form balanced training groups, and pick each
player's work direction and mentor. Each one runs offline, with pause,
chapter buttons and drag-to-rotate. Italian versions of the same animations:
[`pca_rugby_animazione.html`](https://htmlpreview.github.io/?https://raw.githubusercontent.com/matteoguerrucci7-max/Numerical-Methods/main/download/pca_rugby_animazione.html),
[`pca_rugby_direzioni_3d.html`](https://htmlpreview.github.io/?https://raw.githubusercontent.com/matteoguerrucci7-max/Numerical-Methods/main/download/pca_rugby_direzioni_3d.html).

| File | Content | View rendered |
|---|---|---|
| [`pca_rugby_animation_en.html`](download/pca_rugby_animation_en.html) | Whole pipeline in the 3-component space — power method and deflation, players' scores, balanced groups by pairwise swaps, mentors | [open](https://htmlpreview.github.io/?https://raw.githubusercontent.com/matteoguerrucci7-max/Numerical-Methods/main/download/pca_rugby_animation_en.html) |
| [`pca_rugby_work_directions_3d_en.html`](download/pca_rugby_work_directions_3d_en.html) | Work directions in 3D — weakest axis vs the role mean, loadings `s·B[k,j]`, role filter, effect of the training `Δz = BᵀΔx`, mentor | [open](https://htmlpreview.github.io/?https://raw.githubusercontent.com/matteoguerrucci7-max/Numerical-Methods/main/download/pca_rugby_work_directions_3d_en.html) |
| [`pca_rugby_animazione.mp4`](download/pca_rugby_animazione.mp4) | Video of the Italian version of the first animation (72 s, 1920×1200) | — |

## Sources

- G. Puppo, *Metodi Numerici*, lecture notes, Sapienza Università di Roma
  (chapters 1–7).
- A. Greenbaum and T. P. Chartier, *Numerical Methods: Design, Analysis,
  and Computer Implementation of Algorithms*, Princeton University Press,
  2012.
- L. N. Trefethen and D. Bau III, *Numerical Linear Algebra*, SIAM, 1997.
- G. H. Golub and C. F. Van Loan, *Matrix Computations*, 4th ed., Johns
  Hopkins University Press, 2013.
- A. Quarteroni, R. Sacco, F. Saleri, *Numerical Mathematics*, 2nd ed.,
  Springer, 2007.
- IEEE Std 754-2019, *IEEE Standard for Floating-Point Arithmetic*.

Each theorem/definition in the notebook cites which of the above it is
taken from. Copyrighted source material itself (the course PDF, the
textbook) is **not** included in this repository — only original notes,
code, and citations.

## Running it

```bash
pip install -r requirements.txt
jupyter notebook notebooks/L1-L7_numerical_methods.ipynb
```

The notebook is committed with its outputs (numbers, tables, plots)
already computed, so it can also be read directly on GitHub without
running anything.
