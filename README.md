# Markov Chain Monte Carlo (MCMC) Coursework Project

### Random Walk Metropolis Algorithm Implementation

---

## Project Background

This project was completed as part of a University of London coursework assignment in computational statistics.

The objective was to implement a Random Walk Metropolis–Hastings algorithm to sample from a Laplace distribution and evaluate convergence behavior under different proposal scales.

All code and analysis were independently implemented in R.

---

## Target Distribution

The target density is a Laplace distribution centered at zero with scale parameter equal to 1.

Key properties:

* Symmetric around zero
* Sharp peak at the center
* Exponential decay in the tails
* Heavier center compared to a normal distribution

---

## Methodology

### Algorithm

A Random Walk Metropolis algorithm was implemented:

1. At each iteration, propose a new value by adding Gaussian noise.
2. Compute acceptance probability based on the ratio of target densities.
3. Accept or reject the proposal accordingly.

---

## Monte Carlo Simulation

Simulation setting:

* 10,000 iterations
* Proposal scale = 1

Results:

* Estimated mean ≈ -0.0856
* Estimated standard deviation ≈ 1.3484

Histogram and kernel density estimates closely match the theoretical Laplace distribution, confirming successful sampling.

---

## Convergence Diagnostics

To evaluate convergence, multiple independent chains were generated.

The Gelman–Rubin statistic (R-hat) was computed using:

* 4 independent chains
* 2000 iterations per chain

Findings:

* Extremely small proposal scales lead to poor mixing and large R-hat values.
* As the proposal scale increases, R-hat decreases rapidly.
* When proposal scale exceeds approximately 0.5, R-hat stabilizes near 1, indicating convergence.

This demonstrates the importance of proposal tuning in MCMC algorithms.

---

## Sensitivity Analysis

A grid search over proposal scales in the range [0.001, 1] was conducted.

The analysis shows:

* Small proposal variance → slow exploration
* Moderate variance → stable mixing
* Proper tuning significantly improves convergence speed

---

## Repository Structure

```
mcm.Rmd     # Coursework source code
mcmc.pdf    # Final submitted report
README.md   # Project documentation
```

---

## Technical Skills Demonstrated

* Monte Carlo simulation
* Markov Chain Monte Carlo (MCMC)
* Metropolis–Hastings algorithm
* Convergence diagnostics
* Statistical visualization
* Sensitivity analysis
* R programming

---

## Author

Yanlun Xiao

BSc Economics, University of London (SIM)

