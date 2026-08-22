# Numerical Stability Analysis

This project presents a theoretical and computational analysis of single-step and linear multistep numerical schemes for Ordinary Differential Equations (ODEs). It focuses on the **4th-order Runge-Kutta (RK4)** and **3-step Adams-Bashforth (AB3)** methods.

The study investigates algebraic order conditions, maps absolute stability regions in the complex plane, empirically verifies convergence rates via step-halving on the non-linear **Trachenko-Zaccone relaxation equation**, and explores numerical threshold stability on a 2D linear dynamical system.

## Numerical & Mathematical Methods
  * **Order Verification:** Butcher tableau algebraic conditions (RK4) and difference operator expansions (AB3).
  * **Absolute Stability Regions:** Stability function evaluation in the complex plane ($|R(z)| \le 1$) and boundary locus method via root condition $z(\theta) = \rho(e^{i\theta})/\sigma(e^{i\theta})$.
  * **Empirical Convergence:** Step-halving convergence analysis on the non-linear Trachenko-Zaccone equation with log-log order estimations $p = \log_2(err_N / err_{2N})$.
  * **Dynamical System Simulation:** Bisection search for critical step-size ($h_{\text{crit}}$) on coupled stiff/oscillatory linear systems ($\lambda = -0.2 \pm i$).

## Methodology

| Module | Method / Analysis | Key Findings & Verification |
| :--- | :--- | :--- |
| **RK4 Analysis** | Butcher Tableau & Stability Function | Analytically and programmatically confirmed order $p = 4$; mapped 2D absolute stability domain via $R(z) = \sum_{j=0}^4 \frac{z^j}{j!}$. |
| **AB3 Analysis** | Multistep Coefficients & Boundary Locus | Analytically verified order $p = 3$ ( $c_0=\dots=c_3=0, c_4 \neq 0$ ); mapped the bounded stability region using polynomial root evaluation (`polyroot`). |
| **Non-linear Problem** | Trachenko-Zaccone Equation | Tested across $N = 5 \cdot 2^k$ steps against high-precision `deSolve` reference solutions; log-log slope fits confirmed empirical orders of $4.00$ (RK4) and $3.00$ (AB3). |
| **Linear System Stability** | Bisection Search for $h_{\text{crit}}$ | Computed exact stability boundary $h_{\text{crit}}$; simulations at $h > h_{\text{crit}}$ exhibited explosive numerical instability, whereas $h \le h_{\text{crit}}$ matched the analytical damped trajectory. |

## Project Structure
* Source R Markdown implementation (`MNRRZ2025.Rmd`)
* Formatted HTML project report (`MNRRZ2025.html`)
* `images/` – Theoretical theorems, Butcher tables

## Authors
* Wioletta Sudoł
* Sylwester Kubik
