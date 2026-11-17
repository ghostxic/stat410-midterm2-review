# STAT 410 Practice Exam 2, Version 5

Time: 80 minutes. 5 problems, 80 points. Calculator and one 8.5" x 11" sheet allowed. Chi-Square and Cumulative Poisson tables provided.

Show all work. If an answer is a function, say whether it is a p.d.f. or c.d.f. and include its support.

---

## Problem 1 (12 points)

Let Y be a random variable with a Gamma distribution with α = 4 and θ = 3.

**a) (6)** Find P(Y > 15).

**b) (6)** Find a and b such that P(a < Y < b) = 0.90, with P(Y < a) = P(Y > b).

## Problem 2 (20 points)

Let X₁, X₂, …, Xₙ be a random sample from a Poisson distribution with mean λ > 0:

$$P(X=k)=\frac{\lambda^{k}e^{-\lambda}}{k!},\qquad k=0,1,2,\dots$$

**a) (5)** Obtain the maximum likelihood estimator of λ, $\hat\lambda$.

**b) (3)** Find a sufficient statistic for λ.

**c) (4)** Find the Fisher information I(λ).

**d) (4)** Consider estimating P(X = 0) = e^(−λ) with $e^{-\bar X}$. Is $e^{-\bar X}$ unbiased for e^(−λ)? Is it consistent? Justify both answers.

**e) (4)** Suppose λ = 0.8 and n = 5. Find P(X̄ ≤ 0.6).

## Problem 3 (20 points)

Let X₁, X₂, …, Xₙ be a random sample from a N(0, θ) distribution, θ > 0 (mean 0, variance θ):

$$f(x;\theta)=\frac{1}{\sqrt{2\pi\theta}}\,e^{-x^{2}/(2\theta)},\qquad -\infty<x<\infty.$$

**a) (6)** Obtain the maximum likelihood estimator of θ, $\hat\theta$.

**b) (3)** Is $\hat\theta$ an unbiased estimator of θ? Justify your answer.

**c) (4)** Is $\sqrt{\hat\theta}$ an unbiased estimator of the standard deviation σ = √θ? Justify your answer.

**d) (3)** Show that $\hat\theta$ is a consistent estimator of θ.

**e) (4)** Find the Fisher information I(θ).

## Problem 4 (12 points)

Continue with the N(0, θ) sample from Problem 3.

**a) (3)** Find a sufficient statistic for θ.

**b) (5)** Suggest a confidence interval for θ with (1 − α)100% confidence level. Hint: Xᵢ²/θ has a χ²(1) distribution.

**c) (4)** Suppose n = 6 and the data are −2.0, −1.0, 0.5, 1.5, 2.5, 3.0. Construct a 90% confidence interval for θ.

## Problem 5 (16 points)

Let U₁, U₂, …, Uₙ be a random sample from a Uniform(0, 1) distribution.

**a) (6)** Find the probability distribution of Y = −2 ln U₁. Name the distribution.

**b) (4)** Suppose n = 5. Find c such that P(−2 ∑ ln Uᵢ > c) = 0.10.

**c) (6)** Let Mₙ = max Uᵢ. Show that Mₙ converges in probability to 1.

---
---

# Answer Key

## Problem 1

**a)** P(Y > 15) = P(X ≤ α − 1 = 3), where X is Poisson(15/θ = 5).

P(Poisson(5) ≤ 3) = **0.265**.

**b)** 2Y/θ = 2Y/3 has a χ²(2α = 8) distribution, so Y = 1.5·χ²(8).

χ²₀.₉₅(8) = 2.733, χ²₀.₀₅(8) = 15.51.

a = 1.5 × 2.733 = **4.10**, b = 1.5 × 15.51 = **23.27**.

## Problem 2

**a)** L(λ) = ∏ λ^(xᵢ) e^(−λ)/xᵢ! = λ^(∑xᵢ) e^(−nλ) / ∏ xᵢ!.

ln L(λ) = (∑xᵢ) ln λ − nλ − ∑ ln(xᵢ!).

d/dλ: ∑xᵢ/λ − n = 0 ⟹ $\hat\lambda=\bar X$.

**b)** ∏ f(xᵢ; λ) = [λ^(∑xᵢ) e^(−nλ)] · [1/∏ xᵢ!]. By the Factorization Theorem, **Y = ∑ Xᵢ** is sufficient for λ (so is X̄).

**c)** ln f = x ln λ − λ − ln x!. ∂/∂λ = x/λ − 1. ∂²/∂λ² = −x/λ².

I(λ) = E(X)/λ² = λ/λ² = **1/λ**.

**d)** Unbiased? g(x) = e^(−x) is strictly convex and X̄ is not constant, so by Jensen's Inequality

E(e^(−X̄)) > e^(−E(X̄)) = e^(−λ). **Not unbiased** (it overestimates).

Consistent? By WLLN, X̄ → λ in probability, and g(x) = e^(−x) is continuous, so e^(−X̄) → e^(−λ) in probability. **Yes, consistent.**

**e)** ∑Xᵢ is Poisson(nλ = 4). P(X̄ ≤ 0.6) = P(∑Xᵢ ≤ 3) = P(Poisson(4) ≤ 3) = **0.433**.

## Problem 3

**a)** L(θ) = (2πθ)^(−n/2) exp{−∑xᵢ²/(2θ)}.

ln L(θ) = −(n/2) ln(2π) − (n/2) ln θ − ∑xᵢ²/(2θ).

d/dθ: −n/(2θ) + ∑xᵢ²/(2θ²) = 0 ⟹ $\hat\theta=\dfrac{1}{n}\sum X_i^{2}$.

**b)** E(X²) = Var(X) + [E(X)]² = θ + 0 = θ. E($\hat\theta$) = (1/n) · nθ = θ. **Yes, unbiased.**

**c)** g(x) = √x is strictly concave and $\hat\theta$ is not constant, so by Jensen's Inequality

E(√$\hat\theta$) < √E($\hat\theta$) = √θ. **Not unbiased** (it underestimates σ).

**d)** By WLLN applied to X₁², X₂², …, $\hat\theta$ = (1/n)∑Xᵢ² → E(X²) = θ in probability.

**e)** ln f = −(1/2) ln(2π) − (1/2) ln θ − x²/(2θ).

∂/∂θ = −1/(2θ) + x²/(2θ²). ∂²/∂θ² = 1/(2θ²) − x²/θ³.

I(θ) = −1/(2θ²) + E(X²)/θ³ = −1/(2θ²) + 1/θ² = **1/(2θ²)**.

## Problem 4

**a)** ∏ f(xᵢ; θ) = [θ^(−n/2) exp{−∑xᵢ²/(2θ)}] · [(2π)^(−n/2)]. By the Factorization Theorem, **Y = ∑ Xᵢ²** is sufficient for θ.

**b)** Xᵢ/√θ is N(0, 1), so Xᵢ²/θ is χ²(1) and ∑Xᵢ²/θ has a χ²(n) distribution.

P(χ²_{1−α/2}(n) < ∑Xᵢ²/θ < χ²_{α/2}(n)) = 1 − α.

Confidence interval: $\left(\dfrac{\sum x_i^2}{\chi^2_{\alpha/2}(n)},\ \dfrac{\sum x_i^2}{\chi^2_{1-\alpha/2}(n)}\right)$.

**c)** ∑xᵢ² = 4 + 1 + 0.25 + 2.25 + 6.25 + 9 = 22.75. n = 6.

χ²₀.₀₅(6) = 12.59, χ²₀.₉₅(6) = 1.635.

(22.75/12.59, 22.75/1.635) = **(1.807, 13.91)**.

(For reference, $\hat\theta$ = 22.75/6 ≈ 3.79.)

## Problem 5

**a)** 0 < u < 1 ⟹ y = −2 ln u > 0.

F_Y(y) = P(−2 ln U ≤ y) = P(U ≥ e^(−y/2)) = 1 − e^(−y/2), y > 0.

p.d.f. f_Y(y) = (1/2) e^(−y/2), y > 0. This is Exponential with mean 2 = Gamma(α = 1, θ = 2) = **χ²(2)**.

**b)** −2∑ ln Uᵢ is a sum of 5 independent χ²(2), so it is χ²(10).

c = χ²₀.₁₀(10) = **15.99**.

**c)** F_U(u) = u, 0 < u < 1, so P(Mₙ ≤ m) = mⁿ.

Let 0 < ε ≤ 1. Since Mₙ < 1,

P(|Mₙ − 1| ≥ ε) = P(Mₙ ≤ 1 − ε) = (1 − ε)ⁿ → 0 as n → ∞.

For ε > 1 the probability is 0. So Mₙ → 1 in probability.
