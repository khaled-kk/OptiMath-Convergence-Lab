# OptiMath: Newton-Raphson vs. Gradient Descent

A short Python notebook that minimises a two-variable quadratic with a Newton-Raphson-style iteration and with gradient descent, and plots how fast each converges.

## What it does

- Objective: f(x1, x2) = (x1 - 2)^2 + (x2 - 2)^2, minimum at (2, 2).
- **Newton-Raphson:** updates each variable as x <- x - f(x1, x2) / f'(x) (root-finding form, using the partial derivative 2(2x - 4) for each coordinate) until |f| is below a tolerance or a maximum number of steps is reached.
- **Gradient descent:** updates each variable as x <- x - learning_rate * 2(2x - 4) for a fixed number of iterations.
- Starting point, tolerance, learning rate and step limit are read with `input()`.
- Prints the iterates and plots x1 and x2 against the iteration number for each method, then both methods on one chart.

## Tech stack

Python 3, Matplotlib (no other libraries). Written in Google Colab.

## Repository contents

| File | Description |
|------|-------------|
| `newton_raphson_vs_gradient_descent.ipynb` | Both methods, printed iterates and convergence plots |

## Results

Saved notebook outputs, starting from (0, 0):

| Method | Settings | Iterations | Final x1 = x2 |
|--------|----------|------------|---------------|
| Newton-Raphson | tolerance 1e-7, max 20 steps | 14 (stopped at tolerance) | 1.99987793 |
| Gradient descent | learning rate 0.1, 30 steps | 30 | 1.99999926 |

Because f has a double root at the minimum, the Newton-Raphson iteration halves the distance to 2 at each step (linear rather than quadratic convergence). Gradient descent with learning rate 0.1 shrinks the distance by a factor of 0.6 per step.

## How to run

Open the notebook in [Google Colab](https://colab.research.google.com/github/khaled-kk/optimath-convergence-lab/blob/main/newton_raphson_vs_gradient_descent.ipynb) or in Jupyter, run the cells, and enter the starting guesses and parameters when prompted (the saved run used 0, 0, 1e-7, 20 for Newton-Raphson and 0, 0, 0.1, 30 for gradient descent).

---
*Developed by Khaled Walid*
