# STAT 410 Exam 2: Topic Summary

Exam 2: Thursday, November 19, 7:00 - 8:30 pm, 114 David Kinley Hall.
Allowed: calculator, one 8.5" x 11" sheet (both sides). Provided: Chi-Square table, Cumulative Poisson table.

## What is on the exam (from the Canvas list)

| On the exam | Crossed off (not on the exam) |
|---|---|
| { Functions of One Random Variable, 1 → 1 } | Mean Squared Error |
| { Order Statistics } | Markov's Inequality |
| Gamma, Chi-Square, Poisson Distributions | Chebyshev's Inequality |
| Point Estimation | Convergence in Distribution |
| Method of Moments | Central Limit Theorem |
| Maximum Likelihood Method | Δ-Method |
| Unbiased Estimators | Efficiency of Estimators |
| Jensen's Inequality | |
| Convergence in Probability | |
| Weak Law of Large Numbers | |
| Consistent Estimators | |
| Confidence Intervals | |
| Sufficient Statistics | |
| Fisher Information | |

The first two items are in braces on Canvas (older material, carried over from before Exam 1).

## Exam format (modeled on Exam 1)

Exam 1 had 5 multi-part problems, 80 points, free response, and reused one distribution across several problems. Answers that are functions must say p.d.f. or c.d.f. and include the support. The practice exams follow that format.

## Key facts by topic

### Gamma, Chi-Square, Poisson (Week 8)

- Gamma(α, θ): $f(x)=\dfrac{1}{\Gamma(\alpha)\theta^{\alpha}}x^{\alpha-1}e^{-x/\theta}$, $x>0$. $E(X)=\alpha\theta$, $Var(X)=\alpha\theta^2$. With $\lambda = 1/\theta$: $E=\alpha/\lambda$, $Var=\alpha/\lambda^2$.
- $\Gamma(n)=(n-1)!$, $\Gamma(x)=(x-1)\Gamma(x-1)$, $\Gamma(1/2)=\sqrt{\pi}$.
- Gamma-Poisson link (α an integer): if $T_\alpha$ ~ Gamma(α, θ = 1/λ), then $P(T_\alpha > t) = P(X_t \le \alpha-1)$ and $P(T_\alpha \le t)=P(X_t\ge\alpha)$, where $X_t$ ~ Poisson(λt = t/θ).
- Poisson process with rate λ: time of the k-th event is Gamma(α = k, θ = 1/λ).
- Chi-square: χ²(r) = Gamma(α = r/2, θ = 2). $E=r$, $Var=2r$.
- Gamma to chi-square: if Y ~ Gamma(α, θ) then $2Y/\theta$ ~ χ²(2α).
- Sum of independent Gamma(α₁, θ) and Gamma(α₂, θ) is Gamma(α₁ + α₂, θ). Sum of n i.i.d. Exponential(θ) is Gamma(n, θ).
- Typical problems: "k-th arrival during a time window" via the Poisson table; one probability three ways (integral, Poisson, chi-square); find a and b with $P(a<Y<b)=0.90$ from the chi-square table.

### Method of Moments and Maximum Likelihood (Weeks 8-9)

- MoM: compute $E(X)=h(\theta)$, set $\bar X = h(\tilde\theta)$, solve.
- MLE: $L(\theta)=\prod f(x_i;\theta)$, maximize $\ln L$. If the support depends on θ (for example $0<x<\theta$), the derivative does not work: L is monotone and the MLE is max or min of the sample.
- Common trick: find the distribution of the piece the MLE is built from (for example $W=-\ln X$ or $W=X^2$), which is usually Exponential or Gamma. Then sums are Gamma and the Poisson and chi-square tables apply.

### Unbiased estimators and Jensen's inequality (Weeks 8-9)

- $\hat\theta$ is unbiased for θ if $E(\hat\theta)=\theta$ for all θ.
- $E(\bar X)=\mu$, $Var(\bar X)=\sigma^2/n$, $E(S^2)=\sigma^2$.
- Linear g: $E(g(X)) = g(E(X))$. Otherwise use Jensen: if g is strictly convex and X is not constant, $E[g(X)] > g(E[X])$ (reverse for concave). Used to show estimators like $1/\bar X$ are biased, and that $E(S)<\sigma$.
- To fix a bias exactly: if Y ~ Gamma(α, θ) then $E(1/Y)=\dfrac{1}{(\alpha-1)\theta}$ (α > 1).

### Convergence in probability, WLLN, consistency (Week 10)

- $X_n \xrightarrow{P} X$ if for every ε > 0, $P(|X_n-X|\ge\varepsilon)\to 0$.
- WLLN: $\bar X_n \xrightarrow{P} \mu$. Also applies to averages of $g(X_i)$, for example $\frac1n\sum X_i^2 \xrightarrow{P} E(X^2)$.
- If $X_n \xrightarrow{P} a$ and g is continuous at a, then $g(X_n)\xrightarrow{P} g(a)$. Sums and products of convergent sequences converge.
- $\hat\theta$ is consistent if $\hat\theta\xrightarrow{P}\theta$. Standard argument: WLLN plus a continuous function. For max/min estimators compute $P(|\hat\theta-\theta|\ge\varepsilon)$ directly from the c.d.f.
- Convergence in probability does not imply convergence of expected values (Example: $P(X_n=0)=1-1/n$, $P(X_n=n)=1/n$).

### Confidence intervals (Week 11, non-CLT ones)

- Pivot from the Gamma-chi-square link. If $\sum W_i$ ~ Gamma(n, θ), then $\frac{2}{\theta}\sum W_i$ ~ χ²(2n) and a (1 − α)100% interval for θ is
  $\left(\dfrac{2\sum w_i}{\chi^2_{\alpha/2}(2n)},\ \dfrac{2\sum w_i}{\chi^2_{1-\alpha/2}(2n)}\right)$.
- If the parameter is a rate λ with $2\lambda\sum W_i$ ~ χ²(2nα), the interval is $\left(\dfrac{\chi^2_{1-\alpha/2}}{2\sum w_i},\ \dfrac{\chi^2_{\alpha/2}}{2\sum w_i}\right)$.
- Table notation: $\chi^2_{\alpha}(r)$ has area α to the right.

### Sufficient statistics (Week 11)

- Factorization Theorem: Y = u(X₁,…,Xₙ) is sufficient for θ iff the joint p.d.f. factors as $\phi[u(x_1,\dots,x_n);\theta]\cdot h(x_1,\dots,x_n)$.
- Exponential family: if $f(x;\theta)=\exp[p(\theta)K(x)+S(x)+q(\theta)]$ on a support free of θ, then $\sum K(X_i)$ is sufficient.
- If the support depends on θ, write the support with indicator functions; max or min shows up.
- Any one-to-one function of a sufficient statistic is sufficient.
- Conditional check: the distribution of the sample given Y = y does not depend on θ.

### Fisher information (Week 12)

- $I(\theta) = -E\left[\dfrac{\partial^2}{\partial\theta^2}\ln f(X;\theta)\right] = Var\left[\dfrac{\partial}{\partial\theta}\ln f(X;\theta)\right]$.
- Results from class: N(μ, σ²): I(μ) = 1/σ², I(σ²) = 1/(2σ⁴), I(σ) = 2/σ². Exponential mean θ: 1/θ². Exponential rate λ: 1/λ². Poisson: 1/λ. Bernoulli: 1/(p(1−p)). Geometric: 1/(p²(1−p)). Gamma(α known, θ): α/θ².
- Rao-Cramér bound and efficiency are in the same handout but "Efficiency of Estimators" is crossed off.

### Older items in braces

- 1 → 1 transformation: $f_Y(y)=f_X(g^{-1}(y))\left|\dfrac{dx}{dy}\right|$, or go through the c.d.f. Always state the support.
- Order statistics: $F_{\max}(x)=[F(x)]^n$, $P(\min > x) = [1-F(x)]^n$, $f_{\max}(x)=n[F(x)]^{n-1}f(x)$, $f_{\min}(x)=n[1-F(x)]^{n-1}f(x)$.

## Source handouts

Read in full (text and page images): Exam 1 (Version A) answers; Examples for Week 08 (1) and (3) with answers; Week 08 Discussion 3; Examples for Week 10 (1) with answers; Examples for Week 11 (2) and (4); Examples for Week 12 (1) with answers. Practice exams 1-5 were written from these.

Read as extracted text, questions only (formulas come out partly garbled this way): all the other discussion sheets (Week 08 D1, D2, D4, D5; Week 09 D1-D3; Week 10 D1-D3; Week 11 D1-D3; Week 12 D1-D3). Practice exam 6 was written after these.

Skimmed for problem statements only: Homework 6-10.

Not read: the "more" and "even more" example sets (Week 08 (2); Week 09 (1)-(6); Week 10 (2), (6); Week 11 (1), (3), (5), (6), (7); Week 12 (2), (3)) and the worked solutions in the discussion sheets and homework answers. All of these PDFs are in `~/Downloads`.

## Recurring problem pattern in the discussion sheets and homework

The same handful of distributions is carried week to week, one new part per topic:

1. MLE and MoM, then a numeric estimate from 3-6 data points.
2. "Show that W = (some function of X) has a Gamma distribution; identify α and θ" (W = ln X, −ln(1 − X), X², X³, X⁴).
3. A probability about ∑W using the Gamma-Poisson link, or a cutoff using the Gamma-chi-square link.
4. Is the MLE unbiased? If not, construct an unbiased estimator from it, using $E(T^m)=\theta^m\,\Gamma(\alpha+m)/\Gamma(\alpha)$ for T ~ Gamma(α, θ).
5. Is the MoM estimator unbiased? If not, does it over- or underestimate (Jensen)?
6. Consistency of both, "NOT enough to say because it is the MLE"; then "construct a consistent estimator made from ∑Xᵢᵏ".
7. Exact confidence interval from the chi-square pivot ("n is NOT large, no CLT").
8. Sufficient statistic and Fisher information.

Also seen: Poisson-process prediction bounds ("find a such that P(T₄ < a) = 0.90"), a discrete p.m.f. with probabilities θ, 2θ, 1 − 3θ, Uniform(−θ, θ), a confidence interval from max Xᵢ ("find c such that P(cδ < max Xᵢ < δ) = 1 − α"), and P(X₁ + … + Xₙ > n) → 1 by the WLLN.

MSE, Chebyshev/Markov, asymptotic normality, limiting distributions and efficiency parts appear in the same sheets but are crossed off for this exam.
