# STAT 410 Practice Exam 2, Version 1

Time: 80 minutes. 5 problems, 80 points. Calculator and one 8.5" x 11" sheet allowed. Chi-Square and Cumulative Poisson tables provided.

Show all work. If an answer is a function, say whether it is a p.d.f. or c.d.f. and include its support.

Problems 2-5 use the same distribution. Let θ > 0 and let X₁, X₂, …, Xₙ be a random sample from the distribution with probability density function

$$f(x;\theta)=\frac{\theta}{x^{\theta+1}},\qquad x>1,\quad\text{zero otherwise.}$$

---

## Problem 1 (12 points)

**a) (6)** Customers arrive at a help desk according to a Poisson process with an average rate of one customer per 4 minutes. Find the probability that the third customer arrives more than 6 minutes but less than 10 minutes after the desk opens.

**b) (6)** Let Y have a Gamma distribution with α = 4 and θ = 5. Find a and b such that P(a < Y < b) = 0.95, with P(Y < a) = P(Y > b).

## Problem 2 (16 points)

**a) (5)** Find the probability distribution of W = ln X.

**b) (5)** Let Y₁ = min Xᵢ. Find the p.d.f. of Y₁.

**c) (6)** Show that Y₁ converges in probability to 1 as n → ∞.

## Problem 3 (18 points)

**a) (6)** Obtain the maximum likelihood estimator of θ, $\hat\theta$.

**b) (6)** Assume θ > 1. Obtain the method of moments estimator of θ, $\tilde\theta$.

**c) (6)** Suppose n = 5 and x₁ = 1.2, x₂ = 1.5, x₃ = 2.0, x₄ = 2.5, x₅ = 4.0. Compute both estimates.

## Problem 4 (18 points)

**a) (6)** Is $\hat\theta$ an unbiased estimator of θ? If not, construct an unbiased estimator of θ.

**b) (4)** Show that $\hat\theta$ is a consistent estimator of θ.

**c) (4)** Find a sufficient statistic for θ.

**d) (4)** Find the Fisher information I(θ).

## Problem 5 (16 points)

**a) (6)** Suggest a confidence interval for θ with (1 − α)100% confidence level.

**b) (5)** Use the data from Problem 3(c) to construct a 90% confidence interval for θ.

**c) (5)** Suppose θ = 2 and n = 4. Find P(∑ ln Xᵢ > 3).

---
---

# Answer Key

## Problem 1

**a)** Rate λ = 1/4 per minute, so θ = 4. T₃ = time of the third arrival is Gamma(α = 3, θ = 4). Using P(T_α > t) = P(X_t ≤ α − 1) with X_t ~ Poisson(t/4):

P(6 < T₃ < 10) = P(T₃ > 6) − P(T₃ > 10) = P(Poisson(1.5) ≤ 2) − P(Poisson(2.5) ≤ 2) = 0.809 − 0.544 = **0.265**.

**b)** 2Y/θ = 2Y/5 has a χ²(2α = 8) distribution, so Y = 2.5·χ²(8).

χ²₀.₉₇₅(8) = 2.180, χ²₀.₀₂₅(8) = 17.54.

P(2.180 < χ²(8) < 17.54) = 0.95, so a = 2.5 × 2.180 = **5.45**, b = 2.5 × 17.54 = **43.85**.

## Problem 2

**a)** F_X(x) = ∫₁ˣ θ u^(−θ−1) du = 1 − x^(−θ), x > 1.

F_W(w) = P(ln X ≤ w) = P(X ≤ eʷ) = 1 − e^(−θw), w > 0.

W has an **Exponential distribution with mean 1/θ**; p.d.f. f_W(w) = θ e^(−θw), w > 0.

(Jacobian check: x = eʷ, dx/dw = eʷ, f_W(w) = θ e^(−(θ+1)w) · eʷ = θ e^(−θw).)

**b)** P(Y₁ > y) = [P(X > y)]ⁿ = [y^(−θ)]ⁿ = y^(−nθ), y > 1.

c.d.f. F(y) = 1 − y^(−nθ), so p.d.f. **f_{Y₁}(y) = nθ / y^(nθ+1), y > 1** (same family with θ replaced by nθ).

**c)** Let ε > 0. Since Y₁ > 1,

P(|Y₁ − 1| ≥ ε) = P(Y₁ ≥ 1 + ε) = (1 + ε)^(−nθ) → 0 as n → ∞,

because 1 + ε > 1 and θ > 0. Therefore Y₁ → 1 in probability.

## Problem 3

**a)** L(θ) = θⁿ (∏ xᵢ)^(−(θ+1)).

ln L(θ) = n ln θ − (θ + 1) ∑ ln xᵢ.

d/dθ: n/θ − ∑ ln xᵢ = 0 ⟹ $\hat\theta = \dfrac{n}{\sum \ln X_i}$.

(Second derivative −n/θ² < 0, so it is a maximum.)

**b)** E(X) = ∫₁^∞ x · θ x^(−θ−1) dx = θ ∫₁^∞ x^(−θ) dx = θ/(θ − 1) for θ > 1.

Set X̄ = θ̃/(θ̃ − 1): X̄ θ̃ − X̄ = θ̃ ⟹ $\tilde\theta = \dfrac{\bar X}{\bar X - 1}$.

**c)** ∑ ln xᵢ = ln(1.2 · 1.5 · 2.0 · 2.5 · 4.0) = ln 36 ≈ 3.5835. $\hat\theta$ = 5/3.5835 ≈ **1.395**.

x̄ = 11.2/5 = 2.24. $\tilde\theta$ = 2.24/1.24 ≈ **1.806**.

## Problem 4

**a)** Wᵢ = ln Xᵢ are i.i.d. Exponential with mean 1/θ, so Y = ∑ ln Xᵢ is Gamma(α = n, "usual θ" = 1/θ), that is, rate θ.

E(1/Y) = ∫₀^∞ (1/y) · θⁿ y^(n−1) e^(−θy) / Γ(n) dy = θ Γ(n−1)/Γ(n) = θ/(n − 1), n > 1.

E($\hat\theta$) = n E(1/Y) = nθ/(n − 1) ≠ θ. **Not unbiased.**

(Jensen gives the direction without the integral: $\hat\theta$ = g(W̄) with g(x) = 1/x strictly convex, so E($\hat\theta$) > 1/E(W̄) = θ.)

Unbiased estimator: $\dfrac{n-1}{n}\hat\theta = \dfrac{n-1}{\sum \ln X_i}$.

**b)** By WLLN, W̄ = (1/n)∑ ln Xᵢ → E(W) = 1/θ in probability. g(x) = 1/x is continuous at 1/θ > 0. So $\hat\theta$ = g(W̄) → g(1/θ) = θ in probability. $\hat\theta$ is consistent.

**c)** ∏ f(xᵢ; θ) = [θⁿ (∏ xᵢ)^(−(θ+1))] · 1. By the Factorization Theorem, **Y = ∏ Xᵢ** is sufficient for θ (equivalently ∑ ln Xᵢ).

OR: f(x; θ) = exp[−(θ + 1) ln x + ln θ], K(x) = ln x, support free of θ, so ∑ ln Xᵢ is sufficient.

**d)** ln f(x; θ) = ln θ − (θ + 1) ln x.

∂/∂θ = 1/θ − ln x. ∂²/∂θ² = −1/θ².

I(θ) = −E[−1/θ²] = **1/θ²**.

(Check: Var[1/θ − ln X] = Var(W) = 1/θ².)

## Problem 5

**a)** ∑ Wᵢ = ∑ ln Xᵢ is Gamma(α = n, θ_usual = 1/θ), so 2θ ∑ ln Xᵢ has a χ²(2n) distribution.

P(χ²_{1−α/2}(2n) < 2θ ∑ ln Xᵢ < χ²_{α/2}(2n)) = 1 − α.

Confidence interval for θ: $\left(\dfrac{\chi^2_{1-\alpha/2}(2n)}{2\sum \ln x_i},\ \dfrac{\chi^2_{\alpha/2}(2n)}{2\sum \ln x_i}\right)$.

**b)** n = 5, 2n = 10. χ²₀.₉₅(10) = 3.940, χ²₀.₀₅(10) = 18.31. 2∑ ln xᵢ = 7.167.

(3.940/7.167, 18.31/7.167) = **(0.550, 2.555)**.

**c)** ∑ ln Xᵢ is Gamma(α = 4, θ_usual = 1/2), rate λ = 2.

P(T₄ > 3) = P(Poisson(λt = 6) ≤ 3) = **0.151**.

(Chi-square version: P(2·2·∑ ln Xᵢ > 12) = P(χ²(8) > 12).)
