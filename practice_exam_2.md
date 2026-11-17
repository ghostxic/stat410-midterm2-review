# STAT 410 Practice Exam 2, Version 2

Time: 80 minutes. 5 problems, 80 points. Calculator and one 8.5" x 11" sheet allowed. Chi-Square and Cumulative Poisson tables provided.

Show all work. If an answer is a function, say whether it is a p.d.f. or c.d.f. and include its support.

Problems 2-5 use the same distribution. Let λ > 0 and let X₁, X₂, …, Xₙ be a random sample from the distribution with probability density function

$$f(x;\lambda)=\lambda^{2}\,x\,e^{-\lambda x},\qquad x>0,\quad\text{zero otherwise.}$$

(This is a Gamma distribution with α = 2 and "usual θ" = 1/λ.)

---

## Problem 1 (14 points)

Phone calls arrive at a call center according to a Poisson process with an average rate of 2 calls per hour.

**a) (5)** Find the probability that the fourth call arrives more than 1.5 hours after the center opens.

**b) (5)** Find the probability that the fourth call arrives during the second 1.5 hours (between 1.5 and 3 hours after opening).

**c) (4)** Let Xₙ have p.m.f. P(Xₙ = 2) = 1 − 1/n², P(Xₙ = n) = 1/n², n = 3, 4, 5, … . Show that Xₙ converges in probability to 2.

## Problem 2 (14 points)

**a) (7)** Find the probability distribution of V = 1/X.

**b) (7)** Show that $\lambda^{*}=\dfrac{1}{n}\sum_{i=1}^{n}\dfrac{1}{X_i}$ is an unbiased estimator of λ.

## Problem 3 (18 points)

**a) (6)** Obtain the maximum likelihood estimator of λ, $\hat\lambda$.

**b) (4)** Obtain the method of moments estimator of λ, $\tilde\lambda$.

**c) (8)** Is $\hat\lambda$ an unbiased estimator of λ? If not, construct an unbiased estimator of λ of the form c·$\hat\lambda$.

## Problem 4 (18 points)

**a) (5)** Show that $\hat\lambda$ is a consistent estimator of λ.

**b) (5)** Construct a consistent estimator of λ made from ∑ Xᵢ².

**c) (4)** Find a sufficient statistic for λ.

**d) (4)** Find the Fisher information I(λ).

## Problem 5 (16 points)

**a) (6)** Suggest a confidence interval for λ with (1 − α)100% confidence level.

**b) (5)** Suppose n = 4 and x₁ = 0.5, x₂ = 1.0, x₃ = 1.5, x₄ = 3.0. Construct a 90% confidence interval for λ.

**c) (5)** Suppose λ = 2 and n = 3. Find P(X₁ + X₂ + X₃ > 4).

---
---

# Answer Key

## Problem 1

λ = 2 per hour. T₄ = time of the fourth call is Gamma(α = 4, θ = 1/2). X_t = number of calls in t hours is Poisson(2t).

**a)** P(T₄ > 1.5) = P(X₁.₅ ≤ 3) = P(Poisson(3) ≤ 3) = **0.647**.

**b)** P(1.5 < T₄ < 3) = P(T₄ > 1.5) − P(T₄ > 3) = P(Poisson(3) ≤ 3) − P(Poisson(6) ≤ 3) = 0.647 − 0.151 = **0.496**.

**c)** Let ε > 0. For n large enough that n − 2 ≥ ε,

P(|Xₙ − 2| ≥ ε) = P(Xₙ = n) = 1/n² → 0 as n → ∞.

(If ε > n − 2 the probability is 0.) So Xₙ → 2 in probability.

## Problem 2

**a)** v = 1/x, x = 1/v, dx/dv = −1/v². Support: x > 0 ⟹ v > 0.

f_V(v) = f_X(1/v) · |dx/dv| = λ² (1/v) e^(−λ/v) · (1/v²)

p.d.f. **f_V(v) = (λ²/v³) e^(−λ/v), v > 0**, zero otherwise.

**b)** E(1/X) = ∫₀^∞ (1/x) λ² x e^(−λx) dx = λ ∫₀^∞ λ e^(−λx) dx = λ.

E(λ*) = (1/n) ∑ E(1/Xᵢ) = (1/n) · nλ = λ. So λ* is unbiased for λ.

## Problem 3

**a)** L(λ) = λ^(2n) (∏ xᵢ) e^(−λ∑xᵢ).

ln L(λ) = 2n ln λ + ∑ ln xᵢ − λ ∑ xᵢ.

d/dλ: 2n/λ − ∑ xᵢ = 0 ⟹ $\hat\lambda=\dfrac{2n}{\sum X_i}=\dfrac{2}{\bar X}$.

**b)** E(X) = αθ = 2/λ. Set X̄ = 2/λ̃ ⟹ $\tilde\lambda = \dfrac{2}{\bar X}$ (same as the MLE).

**c)** Y = ∑ Xᵢ is Gamma(α = 2n, rate λ).

E(1/Y) = ∫₀^∞ (1/y) λ^(2n) y^(2n−1) e^(−λy)/Γ(2n) dy = λ Γ(2n − 1)/Γ(2n) = λ/(2n − 1).

E($\hat\lambda$) = 2n · λ/(2n − 1) ≠ λ. **Not unbiased** (it overestimates, as Jensen predicts for the convex g(x) = 2/x).

c = (2n − 1)/(2n): $\dfrac{2n-1}{2n}\hat\lambda=\dfrac{2n-1}{\sum X_i}$ is unbiased for λ.

## Problem 4

**a)** By WLLN, X̄ → E(X) = 2/λ in probability. g(x) = 2/x is continuous at 2/λ. So $\hat\lambda$ = g(X̄) → g(2/λ) = λ in probability.

**b)** E(X²) = Var(X) + [E(X)]² = 2/λ² + 4/λ² = 6/λ².

By WLLN, (1/n)∑ Xᵢ² → 6/λ² in probability. g(x) = √(6/x) is continuous at 6/λ², and g(6/λ²) = λ.

$\sqrt{\dfrac{6n}{\sum X_i^2}}$ is a consistent estimator of λ.

**c)** ∏ f(xᵢ; λ) = [λ^(2n) e^(−λ∑xᵢ)] · [∏ xᵢ]. By the Factorization Theorem, **Y = ∑ Xᵢ** is sufficient for λ.

OR: f = exp[−λx + ln x + 2 ln λ], K(x) = x.

**d)** ln f = 2 ln λ + ln x − λx. ∂/∂λ = 2/λ − x. ∂²/∂λ² = −2/λ².

I(λ) = **2/λ²**. (Check: Var(2/λ − X) = Var(X) = 2/λ².)

## Problem 5

**a)** ∑ Xᵢ is Gamma(α = 2n, θ_usual = 1/λ), so 2λ∑Xᵢ has a χ²(4n) distribution.

P(χ²_{1−α/2}(4n) < 2λ∑Xᵢ < χ²_{α/2}(4n)) = 1 − α.

Confidence interval: $\left(\dfrac{\chi^2_{1-\alpha/2}(4n)}{2\sum x_i},\ \dfrac{\chi^2_{\alpha/2}(4n)}{2\sum x_i}\right)$.

**b)** n = 4, 4n = 16, ∑xᵢ = 6. χ²₀.₉₅(16) = 7.962, χ²₀.₀₅(16) = 26.30.

(7.962/12, 26.30/12) = **(0.664, 2.192)**.

(For reference, $\hat\lambda$ = 8/6 ≈ 1.333.)

**c)** X₁ + X₂ + X₃ is Gamma(α = 6, rate 2).

P(T₆ > 4) = P(Poisson(2 · 4 = 8) ≤ 5) = **0.191**.
