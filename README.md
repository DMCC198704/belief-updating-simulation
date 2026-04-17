# Belief Updating & Evidence Integration Simulation

## Overview

This project simulates how agents update beliefs in response to sequential, noisy evidence. It is designed to study the dynamics of inference under uncertainty, with a focus on:

- Evidence order effects
- Signal strength and noise structure
- Learning dynamics (update rates)
- Cross-individual differences
- Optimal information sequencing
- Attribution of evidence importance

The system combines Monte Carlo simulation, behavioral modeling, regression analysis, and interpretability methods (including Shapley-style attribution).

---

## Core Model

## Belief Updating Process

We model inference as a sequential updating process in which each agent forms and revises an estimate of an unknown latent variable.

At each step, beliefs are updated according to a delta rule:

\[
\hat{x}_{t+1} = \hat{x}_t + \alpha (e_t - \hat{x}_t)
\]

This can be interpreted as a **prediction error correction mechanism**, where updates are proportional to the discrepancy between expected and observed values.

### Components

- **State estimate (\(\hat{x}_t\))**: current belief about the latent quantity  
- **Evidence (\(e_t\))**: noisy observation drawn from an external information source  
- **Learning rate (\(\alpha\))**: governs how strongly new evidence is incorporated  

### Evidence model

Evidence is generated stochastically:

\[
e_t \sim \mathcal{N}(x^*, \sigma^2)
\]

where \(x^*\) is the true latent value and \(\sigma^2\) controls signal reliability.

This formulation induces variation in learning dynamics as a function of both **agent-level parameters (\(\alpha\))** and **environmental noise structure (\(\sigma\))**.

---

## Key Research Questions

This simulation explores:

- How does ordering of evidence affect final belief accuracy?
- Which types of evidence produce the largest belief updates?
- Do individuals differ meaningfully in learning efficiency?
- Can optimal evidence sequences be identified computationally?
- How well do cognitive traits predict belief accuracy?

---

## 1. Sequential Belief Updating

Agents receive multiple pieces of evidence sequentially and update beliefs step-by-step.

### Features

- Randomized priors
- Individual learning rates
- Noisy Gaussian evidence generation
- Stepwise convergence tracking

### Outputs

- Belief trajectories
- Error convergence curves
- Final estimation accuracy

---

## 2. Evidence Structure & Effectiveness

Different evidence types vary in:

- Noise magnitude
- Informational reliability
- Directional bias (positive / negative / neutral signals)

### Analysis includes:

- Mean update impact per evidence type
- Percent improvement toward true value
- Cross-condition comparisons

---

## 3. Evidence Order Effects

The model tests whether sequencing influences inference quality.

Findings across simulations show:

- Early evidence has disproportionate influence
- Later evidence exhibits diminishing marginal impact
- Ordering can change final error substantially even with identical evidence sets

---

## 4. Multi-Problem Generalization

The framework is tested across multiple synthetic inference tasks with different true values and evidence structures.

This allows:

- Cross-task robustness evaluation
- Participant-level performance comparison
- Stability analysis of learning parameters

---

## 5. Optimal Sequencing of Information

Several strategies are evaluated:

- Greedy sequencing
- Weighted ranking heuristics
- Simulation-based optimization
- Approximate Bayesian optimization

Key insight:

> Ordering information can significantly reduce final estimation error even when content is unchanged.

---

## 6. Behavioral and Cognitive Modeling

Simulated participants are assigned:

- Big Five personality traits
- IQ-like cognitive scores

These variables are tested against performance metrics.

### Result

- Weak and inconsistent predictive power
- Low explanatory value compared to structural simulation variables (α, evidence order, noise)

---

## 7. Regression Analysis

OLS models examine predictors of final error:

- Personality traits (O, C, E, A, N)
- IQ
- Interaction terms

### Summary

- Low R² values (~0.15 or lower)
- Few significant predictors
- High sensitivity to multicollinearity

---

## 8. Evidence Attribution (Shapley Analysis)

To quantify evidence importance:

- Approximate Shapley values computed
- Exact Shapley values computed for comparison

### Outcome

- Stable ranking of evidence usefulness
- High-signal evidence consistently dominates contribution
- Noisy or opinion-based signals contribute weakly or negatively

---

## 9. Key Findings

Across simulations:

- Belief updating is strongly path-dependent
- Evidence order materially affects outcomes
- Learning rates dominate individual differences
- Structural properties of information matter more than static traits
- Evidence usefulness is highly asymmetric

---

## Technologies

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Statsmodels

---

