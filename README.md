
# Doubly Robust Estimator for Dynamic Treatment Degime

Implementing the Doubly Robust Estimator with Augmented Inverse Probability Weighting (AIPW) for bias estimation in multi-stage, multi-treatment dynamic treatment regimes.

## AIPW Estimator Overview

The AIPW estimator is a core tool for causal inference in settings where multiple stages and treatments are involved. It combines the strengths of inverse probability weighting and outcome regression to adjust for confounding, offering robustness even if one of the models is incorrectly specified.

### Formula

The AIPW estimator is expressed as:


$$
\hat{V}_{AIPW}(d) = \mathbb{P}_n[\hat{Q}^d_1(H_1, d_1(H_1))] + \mathbb{P}_n \left[ \sum_{t=1}^T \prod_{i=1}^t \frac{1_{A_i = d_i(H_i)}}{\pi_i(A_i | H_i)} \left(Y_t - \hat{Q}^d_t(H_t, A_t) + \hat{Q}^d_{t+1}(H_{t+1}, d_t(H_{t+1}))\right) \right]
$$



Where:
- $H_t$: History up to time $t$
- $A_t$: Treatment at time $t$
- $Y_t$: Outcome at time $t$
- $d_t(H_t)$: Treatment decision rule based on history at time $t$
- $\pi_i(A_i \mid H_i)$: Propensity score, the probability of treatment $A_i$ given history $H_i$
- $\hat{Q}^d_t$: Estimated outcome model at time $t$





This estimator is particularly useful for estimating causal effects when dealing with complex longitudinal data involving sequential interventions.
