# STAT 410 Practice Exam 2, Version 3

Time: 80 minutes. 5 problems, 80 points. Calculator and one 8.5" x 11" sheet allowed. Chi-Square and Cumulative Poisson tables provided.

Show all work. If an answer is a function, say whether it is a p.d.f. or c.d.f. and include its support.

Problems 2-5 use the same distribution. Let θ > 0 and let X₁, X₂, …, Xₙ be a random sample from the distribution with probability density function

$$f(x;\theta)=\frac{2x}{\theta}\,e^{-x^{2}/\theta},\qquad x>0,\quad\text{zero otherwise.}$$

---

## Problem 1 (12 points)

Let Y be a random variable with a Gamma distribution with α = 3 and θ = 4.

**a) (4)** Find P(Y > 20) using the relationship between the Gamma and Poisson distributions.

**b) (4)** Write P(Y > 20) as a probability about a chi-square random variable. State the degrees of freedom.

**c) (4)** Find c such that P(Y < c) = 0.90.

## Problem 2 (16 points)

**a) (5)** Find the probability distribution of W = X².

**b) (5)** Suppose θ = 4 and n = 5. Find P(max Xᵢ ≤ 3).

**c) (6)** Let Y₁ = min Xᵢ. Show that Y₁ converges in probability to 0 as n → ∞.

## Problem 3 (18 points)

**a) (6)** Obtain the maximum likelihood estimator of θ, $\hat\theta$.

**b) (7)** Obtain the method of moments estimator of θ, $\tilde\theta$. Hint: Γ(3/2) = √π / 2.

**c) (5)** Suppose n = 4 and x₁ = 1, x₂ = 2, x₃ = 3, x₄ = 4. Compute both estimates.

## Problem 4 (18 points)

**a) (4)** Is $\hat\theta$ an unbiased estimator of θ? Justify your answer.

**b) (5)** Is $\tilde\theta$ an unbiased estimator of θ? Justify your answer.

**c) (5)** Show that $\tilde\theta$ is a consistent estimator of θ.

**d) (4)** Find the Fisher information I(θ).

## Problem 5 (16 points)

**a) (3)** Find a sufficient statistic for θ.

**b) (5)** Suggest a confidence interval for θ with (1 − α)100% confidence level.

**c) (4)** Use the data from Problem 3(c) to construct a 90% confidence interval for θ.

**d) (4)** Suppose θ = 4 and n = 5. Find P(∑ Xᵢ² > 36).

---
---

# Answer Key

## Problem 1

**a)** P(Y > 20) = P(X ≤ α − 1 = 2), where X is Poisson(20/θ = 5).

P(Poisson(5) ≤ 2) = **0.125**.

**b)** 2Y/θ = Y/2 has a χ²(2α = 6) distribution.

P(Y > 20) = P(Y/2 > 10) = **P(χ²(6) > 10)**.

**c)** Y = 2·χ²(6). P(χ²(6) < 10.64) = 0.90 since χ²₀.₁₀(6) = 10.64.

c = 2 × 10.64 = **21.28**.

## Problem 2

**a)** F_X(x) = ∫₀ˣ (2u/θ) e^(−u²/θ) du = 1 − e^(−x²/θ), x > 0.

F_W(w) = P(X² ≤ w) = P(X ≤ √w) = 1 − e^(−w/θ), w > 0.

W has an **Exponential distribution with mean θ**; p.d.f. f_W(w) = (1/θ) e^(−w/θ), w > 0.

**b)** P(max Xᵢ ≤ 3) = [F_X(3)]⁵ = (1 − e^(−9/4))⁵ = (0.8946)⁵ ≈ **0.573**.

**c)** P(Y₁ > y) = [1 − F_X(y)]ⁿ = e^(−ny²/θ), y > 0.

Let ε > 0. P(|Y₁ − 0| ≥ ε) = P(Y₁ ≥ ε) = e^(−nε²/θ) → 0 as n → ∞. So Y₁ → 0 in probability.

## Problem 3

**a)** L(θ) = 2ⁿ (∏ xᵢ) θ^(−n) e^(−∑xᵢ²/θ).

ln L(θ) = n ln 2 + ∑ ln xᵢ − n ln θ − (1/θ) ∑ xᵢ².

d/dθ: −n/θ + ∑xᵢ²/θ² = 0 ⟹ $\hat\theta=\dfrac{1}{n}\sum X_i^{2}$.

**b)** E(X) = E(W^(1/2)) = ∫₀^∞ w^(1/2) (1/θ) e^(−w/θ) dw = θ^(1/2) Γ(3/2) = √(πθ)/2.

Set X̄ = √(π θ̃)/2 ⟹ $\tilde\theta=\dfrac{4\bar X^{2}}{\pi}$.

**c)** ∑xᵢ² = 1 + 4 + 9 + 16 = 30. $\hat\theta$ = 30/4 = **7.5**.

x̄ = 2.5. $\tilde\theta$ = 4(6.25)/π = 25/π ≈ **7.958**.

## Problem 4

**a)** E(X²) = E(W) = θ. E($\hat\theta$) = (1/n) · nθ = θ. **Yes, unbiased.**

**b)** g(x) = 4x²/π is strictly convex and X̄ is not constant. By Jensen's Inequality,

E($\tilde\theta$) = E[g(X̄)] > g(E(X̄)) = (4/π)(πθ/4) = θ. **Not unbiased.**

OR exactly: Var(X) = θ − πθ/4, so E(X̄²) = Var(X̄) + [E(X̄)]² = θ(1 − π/4)/n + πθ/4, and

E($\tilde\theta$) = θ + (4/π − 1)θ/n > θ.

**c)** By WLLN, X̄ → E(X) = √(πθ)/2 in probability. g(x) = 4x²/π is continuous. So $\tilde\theta$ = g(X̄) → g(√(πθ)/2) = θ in probability.

**d)** ln f = ln 2 + ln x − ln θ − x²/θ.

∂/∂θ = −1/θ + x²/θ². ∂²/∂θ² = 1/θ² − 2x²/θ³.

I(θ) = −E[1/θ² − 2X²/θ³] = −1/θ² + 2θ/θ³ = **1/θ²**.

## Problem 5

**a)** ∏ f(xᵢ; θ) = [θ^(−n) e^(−∑xᵢ²/θ)] · [2ⁿ ∏ xᵢ]. By the Factorization Theorem, **Y = ∑ Xᵢ²** is sufficient for θ.

**b)** Wᵢ = Xᵢ² are i.i.d. Exponential(θ), so ∑Xᵢ² is Gamma(α = n, θ) and (2/θ)∑Xᵢ² has a χ²(2n) distribution.

P(χ²_{1−α/2}(2n) < (2/θ)∑Xᵢ² < χ²_{α/2}(2n)) = 1 − α.

Confidence interval: $\left(\dfrac{2\sum x_i^2}{\chi^2_{\alpha/2}(2n)},\ \dfrac{2\sum x_i^2}{\chi^2_{1-\alpha/2}(2n)}\right)$.

**c)** n = 4, 2n = 8, 2∑xᵢ² = 60. χ²₀.₀₅(8) = 15.51, χ²₀.₉₅(8) = 2.733.

(60/15.51, 60/2.733) = **(3.87, 21.95)**.

**d)** ∑Xᵢ² is Gamma(α = 5, θ = 4).

P(T₅ > 36) = P(Poisson(36/4 = 9) ≤ 4) = **0.055**.

(Chi-square version: P(χ²(10) > 18).)
