# Probabilistic Modeling of Inter-Arrival Times Between Phone Checks

Final Project — Probability 1

Faculty of Mathematics, Statistics and Computer Science

Instructor: Dr. Ramin Kazemi | Project Supervisor: Parsa Setayesh

Author: Matin Mohammadi


---

## Overview

This project models the real-world random phenomenon of **the time interval between two consecutive instances of checking a mobile phone** using the **Exponential Distribution**. The objective is to bridge the gap between abstract probability theory and its application to an observable, real-world process.

The random variable $X$ (measured in minutes) is defined as:

$$X \sim \text{Exponential}(\lambda), \qquad \lambda = \frac{1}{12}$$

based on the empirical observation that, on average, the phone is checked once every **12 minutes**.

## Project Objectives

In accordance with the five stages specified in the project guidelines:

| Stage | Title | Description |
|---|---|---|
| 1 | The "Why" | Mathematical justification for selecting the exponential distribution, derived from a Poisson process |
| 2 | The "Present" | Computation of $E[X]$, $\text{Var}(X)$, and $P(X > c)$ for a critical threshold $c = 45$ minutes |
| 3 | The "Future" | Conditional scenario analysis, the memoryless property, and the application of LOTUS |
| 4 | The Reality Check | Monte Carlo simulation with 150,000 iterations and empirical validation of the model |
| 5 | Conclusion | Interpretation of results and their practical implications |

## Summary of Results

| Quantity | Theoretical Value | Simulated Value | Relative Error |
|---|---|---|---|
| $E[X]$ | 12.00 | 11.99 | approx. 0.08% |
| $\text{Var}(X)$ | 144.00 | 144.72 | approx. 0.50% |
| $P(X > 45)$ | 0.0235 | 0.0240 | approx. 2.19% |
| $E[g(X)]$, where $g(X) = \min(X, 15)$ (LOTUS) | 8.5619 | 8.5467 | approx. 0.18% |

The close agreement between theoretical and simulated values, consistent with the **Law of Large Numbers (LLN)**, supports the validity of the exponential model.

## Tools and Libraries

- Python 3
- numpy
- pandas
- matplotlib
- scipy (stats, integrate)

## Project Structure

```
.
├── Main.ipynb      Main notebook containing the mathematical analysis, simulation code, and figures
└── README.md       This file
```

## Usage

```bash
pip install numpy pandas matplotlib scipy jupyter
jupyter notebook Main.ipynb
```

Execute the cells sequentially to reproduce the analysis.

## Principal Figures

- Comparison of the simulated data histogram against the theoretical exponential PDF
- Convergence of the running sample mean to the theoretical $E[X]$, illustrating the Law of Large Numbers

## Conclusion

The memoryless property of the exponential distribution implies that the elapsed time since the last phone check provides no information about the time remaining until the next check. This finding has practical implications for the design of notification management strategies and interventions aimed at improving sustained attention.
