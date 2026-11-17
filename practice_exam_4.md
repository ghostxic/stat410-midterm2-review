# STAT 410 Practice Exam 2, Version 4

Time: 80 minutes. 5 problems, 80 points. Calculator and one 8.5" x 11" sheet allowed. Chi-Square and Cumulative Poisson tables provided.

Show all work. If an answer is a function, say whether it is a p.d.f. or c.d.f. and include its support.

Problems 2-4 use the same distribution. Let θ > 0 and let X₁, X₂, …, Xₙ be a random sample from the distribution with probability density function

$$f(x;\theta)=\frac{3x^{2}}{\theta^{3}},\qquad 0<x<\theta,\quad\text{zero otherwise.}$$

---

## Problem 1 (10 points)

Customers enter a store according to a Poisson process with an average rate of one customer per 2 minutes.

**a) (5)** Find the probability that the sixth customer enters more than 8 minutes after the store opens.

**b) (5)** Find the probability that the sixth customer enters more than 8 minutes but less than 16 minutes after the store opens.

## Problem 2 (18 points)

**a) (5)** Obtain the method of moments estimator of θ, $\tilde\theta$.

**b) (4)** Is $\tilde\theta$ an unbiased estimator of θ? Justify your answer.

**c) (4)** Show that $\tilde\theta$ is a consistent estimator of θ.

**d) (5)** Find Var($\tilde\theta$).

## Problem 3 (20 points)

**a) (5)** Obtain the maximum likelihood estimator of θ, $\hat\theta$.

**b) (5)** Find the p.d.f. of $\hat\theta$.

**c) (5)** Is $\hat\theta$ an unbiased estimator of θ? If not, construct an unbiased estimator of θ of the form c·$\hat\theta$.

**d) (5)** Show that $\hat\theta$ is a consistent estimator of θ.

## Problem 4 (14 points)

**a) (5)** Find a sufficient statistic for θ.

**b) (4)** Suppose n = 4 and x₁ = 1.1, x₂ = 1.8, x₃ = 2.1, x₄ = 2.4. Compute the method of moments estimate, the maximum likelihood estimate, and the unbiased estimate from Problem 3(c).

**c) (5)** Suppose θ = 2 and n = 4. Find P(max Xᵢ < 1.8) and P(min Xᵢ < 1).

## Problem 5 (18 points)

The lifetime (in years) of a certain component has an Exponential distribution with mean θ:

$$f(x;\theta)=\frac{1}{\theta}e^{-x/\theta},\qquad x>0.$$

Let X₁, X₂, …, Xₙ be a random sample of lifetimes.

**a) (4)** Find the Fisher information I(θ).

**b) (5)** Suggest a confidence interval for θ with (1 − α)100% confidence level.

**c) (4)** Suppose n = 6 and the observed lifetimes add up to ∑xᵢ = 30. Construct a 90% confidence interval for θ.

**d) (5)** Suppose θ = 4 and n = 6. Find P(∑ Xᵢ > 40).

---
---

# Answer Key

## Problem 1

Rate λ = 1/2 per minute. T₆ is Gamma(α = 6, θ = 2). X_t = number of customers in t minutes is Poisson(t/2).

**a)** P(T₆ > 8) = P(X₈ ≤ 5) = P(Poisson(4) ≤ 5) = **0.785**.

**b)** P(8 < T₆ < 16) = P(Poisson(4) ≤ 5) − P(Poisson(8) ≤ 5) = 0.785 − 0.191 = **0.594**.

## Problem 2

**a)** E(X) = ∫₀^θ x · 3x²/θ³ dx = (3/θ³)(θ⁴/4) = 3θ/4.

Set X̄ = 3θ̃/4 ⟹ $\tilde\theta=\dfrac{4}{3}\bar X$.

**b)** E($\tilde\theta$) = (4/3) E(X̄) = (4/3)(3θ/4) = θ. **Yes, unbiased.**

**c)** By WLLN, X̄ → 3θ/4 in probability, so $\tilde\theta$ = (4/3)X̄ → (4/3)(3θ/4) = θ in probability.

**d)** E(X²) = ∫₀^θ x² · 3x²/θ³ dx = 3θ²/5.

Var(X) = 3θ²/5 − 9θ²/16 = (48 − 45)θ²/80 = 3θ²/80.

Var($\tilde\theta$) = (16/9) · Var(X)/n = (16/9)(3θ²/80)/n = **θ²/(15n)**.

## Problem 3

**a)** L(θ) = 3ⁿ (∏ xᵢ²) / θ^(3n) if θ > max xᵢ, and L(θ) = 0 if θ < max xᵢ.

On θ > max xᵢ, L(θ) is decreasing in θ, so it is largest at the smallest allowed value.

$\hat\theta=\max X_i$.

(Setting the derivative of ln L equal to zero does not work here: −3n/θ is never 0.)

**b)** F_X(x) = x³/θ³, 0 < x < θ.

F_max(y) = [F_X(y)]ⁿ = y^(3n)/θ^(3n), 0 < y < θ.

p.d.f. **f_max(y) = 3n y^(3n−1) / θ^(3n), 0 < y < θ**, zero otherwise.

**c)** E($\hat\theta$) = ∫₀^θ y · 3n y^(3n−1)/θ^(3n) dy = 3nθ/(3n + 1) ≠ θ. **Not unbiased** (it underestimates).

c = (3n + 1)/(3n): $\dfrac{3n+1}{3n}\max X_i$ is unbiased for θ.

**d)** Let 0 < ε < θ. Since $\hat\theta$ < θ,

P(|$\hat\theta$ − θ| ≥ ε) = P(max Xᵢ ≤ θ − ε) = ((θ − ε)/θ)^(3n) = (1 − ε/θ)^(3n) → 0 as n → ∞.

(For ε ≥ θ the probability is 0.) So $\hat\theta$ → θ in probability.

## Problem 4

**a)** Write f(x; θ) = (3x²/θ³) · I{x < θ} · I{x > 0}.

∏ f(xᵢ; θ) = [θ^(−3n) · I{max xᵢ < θ}] · [3ⁿ ∏ xᵢ² · I{min xᵢ > 0}].

By the Factorization Theorem, **Y = max Xᵢ** is sufficient for θ.

(The exponential-family theorem cannot be used because the support depends on θ.)

**b)** x̄ = 7.4/4 = 1.85. $\tilde\theta$ = (4/3)(1.85) ≈ **2.467**.

$\hat\theta$ = max xᵢ = **2.4**.

Unbiased: (13/12)(2.4) = **2.6**.

**c)** F_X(x) = x³/8.

P(max Xᵢ < 1.8) = [(1.8/2)³]⁴ = 0.9¹² ≈ **0.282**.

P(min Xᵢ < 1) = 1 − [P(X > 1)]⁴ = 1 − (1 − 1/8)⁴ = 1 − 0.875⁴ ≈ **0.414**.

## Problem 5

**a)** ln f = −ln θ − x/θ. ∂/∂θ = −1/θ + x/θ². ∂²/∂θ² = 1/θ² − 2x/θ³.

I(θ) = −1/θ² + 2E(X)/θ³ = −1/θ² + 2/θ² = **1/θ²**.

**b)** ∑Xᵢ is Gamma(α = n, θ), so (2/θ)∑Xᵢ has a χ²(2n) distribution.

P(χ²_{1−α/2}(2n) < (2/θ)∑Xᵢ < χ²_{α/2}(2n)) = 1 − α.

Confidence interval: $\left(\dfrac{2\sum x_i}{\chi^2_{\alpha/2}(2n)},\ \dfrac{2\sum x_i}{\chi^2_{1-\alpha/2}(2n)}\right)$.

**c)** 2n = 12, 2∑xᵢ = 60. χ²₀.₀₅(12) = 21.03, χ²₀.₉₅(12) = 5.226.

(60/21.03, 60/5.226) = **(2.853, 11.48)**.

**d)** ∑Xᵢ is Gamma(α = 6, θ = 4).

P(T₆ > 40) = P(Poisson(40/4 = 10) ≤ 5) = **0.067**.
