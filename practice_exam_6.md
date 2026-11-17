# STAT 410 Practice Exam 2, Version 6

Time: 80 minutes. 5 problems, 80 points. Calculator and one 8.5" x 11" sheet allowed. Chi-Square and Cumulative Poisson tables provided.

Show all work. If an answer is a function, say whether it is a p.d.f. or c.d.f. and include its support.

This version targets problem types that appear in the discussion sheets and homework but not in Versions 1-5: prediction bounds, "show W has a Gamma distribution" with α > 1, a discrete distribution, and a confidence interval built from max Xᵢ.

---

## Problem 1 (14 points)

In Anytown, power outages occur according to a Poisson process with an average rate of 0.5 per day.

**a) (5)** Find the probability that the fourth outage occurs more than 6 days but less than 10 days after January 1.

**b) (5)** Construct a 90% prediction upper bound for the time of the fourth outage. That is, find a such that P(T₄ < a) = 0.90.

**c) (4)** Let X₁, X₂, … be i.i.d. with p.d.f. f(x) = (1/2)e^(−x/2), x > 0. Show that P(X₁ + X₂ + … + Xₙ > n) → 1 as n → ∞.

## Problem 2 (20 points)

Let β > 0 and let X₁, X₂, …, Xₙ be a random sample from the distribution with probability density function

$$f(x;\beta)=\frac{3}{2\beta^{3}}\,x^{8}\,e^{-x^{3}/\beta},\qquad x>0,\quad\text{zero otherwise.}$$

**a) (5)** Show that W = X³ has a Gamma distribution. What are its parameters α and θ?

**b) (5)** Obtain the maximum likelihood estimator of β, $\hat\beta$.

**c) (3)** Is $\hat\beta$ an unbiased estimator of β? Justify your answer.

**d) (3)** Is $\hat\beta$ a consistent estimator of β? Justify your answer. (It is not enough to say "because it is the maximum likelihood estimator".)

**e) (4)** Construct a consistent estimator of β made from ∑ Xᵢ⁶. Does it underestimate or overestimate β on average?

## Problem 3 (16 points)

Continue with the distribution from Problem 2.

**a) (3)** Find a sufficient statistic for β.

**b) (4)** Find the Fisher information I(β).

**c) (5)** Suppose n = 3 and x₁ = 1.0, x₂ = 1.5, x₃ = 2.0. Construct a 90% confidence interval for β.

**d) (4)** Suppose β = 2 and n = 2. Find P(X₁³ + X₂³ > 16).

## Problem 4 (16 points)

Let 0 < θ < 1/4 and let X₁, X₂, …, Xₙ be a random sample from the discrete distribution with probability mass function

P(X = 0) = θ,  P(X = 1) = 3θ,  P(X = 2) = 1 − 4θ.

**a) (4)** Obtain the method of moments estimator of θ, $\tilde\theta$. Is it unbiased?

**b) (6)** Obtain the maximum likelihood estimator of θ, $\hat\theta$.

**c) (3)** Is $\hat\theta$ an unbiased estimator of θ? Justify your answer.

**d) (3)** A sample of size n = 10 contains one 0, five 1s and four 2s. Compute both estimates.

## Problem 5 (14 points)

Let θ > 0 and let X₁, X₂, …, Xₙ be a random sample from the distribution with probability density function

$$f(x;\theta)=\frac{2x}{\theta^{2}},\qquad 0<x<\theta,\quad\text{zero otherwise.}$$

**a) (4)** Obtain the maximum likelihood estimator of θ, $\hat\theta$.

**b) (4)** Find c such that P(cθ < max Xᵢ < θ) = 1 − α.

**c) (3)** Suppose n = 5 and max xᵢ = 3.2. Use part (b) to construct a 90% confidence interval for θ.

**d) (3)** Find a sufficient statistic for θ.

---
---

# Answer Key

## Problem 1

λ = 0.5 per day, θ = 2. T₄ is Gamma(α = 4, θ = 2). X_t is Poisson(0.5t).

**a)** P(6 < T₄ < 10) = P(T₄ > 6) − P(T₄ > 10) = P(Poisson(3) ≤ 3) − P(Poisson(5) ≤ 3) = 0.647 − 0.265 = **0.382**.

**b)** 2T₄/θ = T₄ has a χ²(2α = 8) distribution (here θ = 2, so T₄ itself is χ²(8)).

P(χ²(8) < 13.36) = 0.90, since χ²₀.₁₀(8) = 13.36. So a = **13.36 days**.

**c)** The Xᵢ are Exponential with mean μ = 2. By WLLN, X̄ₙ → 2 in probability.

P(X₁ + … + Xₙ > n) = P(X̄ₙ > 1) ≥ P(|X̄ₙ − 2| < 1) → 1 as n → ∞.

So P(X₁ + … + Xₙ > n) → 1.

## Problem 2

**a)** w = x³, x = w^(1/3), dx/dw = (1/3)w^(−2/3). Support w > 0.

f_W(w) = f_X(w^(1/3)) · |dx/dw| = (3/(2β³)) w^(8/3) e^(−w/β) · (1/3) w^(−2/3) = (1/(2β³)) w² e^(−w/β), w > 0.

Since Γ(3) = 2, this is $\dfrac{1}{\Gamma(3)\beta^{3}}w^{3-1}e^{-w/\beta}$: **Gamma with α = 3, θ = β**.

**b)** L(β) = (3/2)ⁿ β^(−3n) (∏ xᵢ⁸) e^(−∑xᵢ³/β).

ln L(β) = n ln(3/2) − 3n ln β + 8∑ ln xᵢ − (1/β)∑xᵢ³.

d/dβ: −3n/β + ∑xᵢ³/β² = 0 ⟹ $\hat\beta=\dfrac{\sum X_i^{3}}{3n}=\dfrac{\bar W}{3}$.

**c)** E(W) = αθ = 3β. E($\hat\beta$) = E(W̄)/3 = 3β/3 = β. **Yes, unbiased.**

**d)** By WLLN, W̄ → E(W) = 3β in probability, so $\hat\beta$ = W̄/3 → β in probability. **Yes, consistent.**

**e)** E(X⁶) = E(W²) = Var(W) + [E(W)]² = 3β² + 9β² = 12β².

By WLLN, (1/n)∑Xᵢ⁶ → 12β² in probability. g(x) = √(x/12) is continuous, g(12β²) = β.

$\sqrt{\dfrac{\sum X_i^{6}}{12n}}$ is a consistent estimator of β.

g is strictly concave, so by Jensen's Inequality E[g(·)] < g(12β²) = β: it **underestimates** β on average.

## Problem 3

**a)** ∏ f(xᵢ; β) = [β^(−3n) e^(−∑xᵢ³/β)] · [(3/2)ⁿ ∏ xᵢ⁸]. By the Factorization Theorem, **Y = ∑ Xᵢ³** is sufficient for β.

**b)** ln f = ln(3/2) − 3 ln β + 8 ln x − x³/β.

∂/∂β = −3/β + x³/β². ∂²/∂β² = 3/β² − 2x³/β³.

I(β) = −3/β² + 2E(X³)/β³ = −3/β² + 6β/β³ = **3/β²**.

**c)** ∑Xᵢ³ = ∑Wᵢ is Gamma(α = 3n, θ = β), so (2/β)∑Xᵢ³ has a χ²(6n) distribution.

Confidence interval: $\left(\dfrac{2\sum x_i^3}{\chi^2_{\alpha/2}(6n)},\ \dfrac{2\sum x_i^3}{\chi^2_{1-\alpha/2}(6n)}\right)$.

n = 3, 6n = 18. ∑xᵢ³ = 1 + 3.375 + 8 = 12.375, so 2∑xᵢ³ = 24.75.

χ²₀.₀₅(18) = 28.87, χ²₀.₉₅(18) = 9.390.

(24.75/28.87, 24.75/9.390) = **(0.857, 2.636)**.

(For reference, $\hat\beta$ = 12.375/9 = 1.375.)

**d)** X₁³ + X₂³ is Gamma(α = 6, θ = 2).

P(T₆ > 16) = P(Poisson(16/2 = 8) ≤ 5) = **0.191**.

## Problem 4

**a)** E(X) = 0·θ + 1·3θ + 2·(1 − 4θ) = 2 − 5θ.

Set X̄ = 2 − 5θ̃ ⟹ $\tilde\theta=\dfrac{2-\bar X}{5}$.

E($\tilde\theta$) = (2 − E(X̄))/5 = (2 − (2 − 5θ))/5 = θ. **Unbiased** (linear function of X̄).

**b)** Let N₀, N₁, N₂ be the numbers of 0s, 1s and 2s in the sample, N₀ + N₁ + N₂ = n.

L(θ) = θ^(N₀) (3θ)^(N₁) (1 − 4θ)^(N₂).

ln L(θ) = (N₀ + N₁) ln θ + N₁ ln 3 + N₂ ln(1 − 4θ).

d/dθ: (N₀ + N₁)/θ − 4N₂/(1 − 4θ) = 0

⟹ (N₀ + N₁)(1 − 4θ) = 4N₂θ ⟹ N₀ + N₁ = 4θ(N₀ + N₁ + N₂) = 4nθ.

$\hat\theta=\dfrac{N_0+N_1}{4n}$.

**c)** N₀ + N₁ is Binomial(n, p = θ + 3θ = 4θ), so E(N₀ + N₁) = 4nθ and E($\hat\theta$) = θ. **Yes, unbiased.**

**d)** x̄ = (0 + 5 + 8)/10 = 1.3. $\tilde\theta$ = (2 − 1.3)/5 = **0.14**.

$\hat\theta$ = (1 + 5)/40 = **0.15**.

## Problem 5

**a)** L(θ) = 2ⁿ (∏ xᵢ)/θ^(2n) for θ > max xᵢ, and 0 otherwise. L is decreasing in θ on θ > max xᵢ, so

$\hat\theta=\max X_i$.

**b)** F_X(x) = x²/θ², 0 < x < θ. F_max(y) = (y/θ)^(2n).

P(cθ < max Xᵢ < θ) = 1 − F_max(cθ) = 1 − c^(2n) = 1 − α ⟹ **c = α^(1/(2n))**.

**c)** cθ < max Xᵢ < θ ⟺ max Xᵢ < θ < max Xᵢ / c.

Confidence interval: (max xᵢ, max xᵢ / α^(1/(2n))).

n = 5, α = 0.10: c = 0.10^(1/10) ≈ 0.7943. (3.2, 3.2/0.7943) = **(3.2, 4.03)**.

**d)** ∏ f(xᵢ; θ) = [θ^(−2n) · I{max xᵢ < θ}] · [2ⁿ ∏ xᵢ · I{min xᵢ > 0}]. By the Factorization Theorem, **Y = max Xᵢ** is sufficient for θ.
