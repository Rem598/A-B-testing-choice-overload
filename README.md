# Bayesian A/B Testing: The Paradox of Choice

Does reducing product density improve e-commerce conversions? And which statistical framework gives you a more useful answer?

---

## The Question

Hick's Law predicts that more choices increase cognitive load and reduce decision speed. Applied to e-commerce: does showing 6 products on a category page convert better than showing 24?

That is the business question. But this project is also a methodological comparison. The same experiment is analyzed through two frameworks — Frequentist and Bayesian — to show why the choice of framework changes what you can actually do with the result.

**Condition A:** High density (24 products per page).
**Condition B:** Low density (6 products per page).

---

## Key Findings

**The low-density layout wins, with 98.4% probability of superiority and approximately 40% lift in revenue per user.**

But the more important finding is the methodological one.

**The Frequentist p-value was unstable throughout the experiment.**

As data accumulated across 5,100 sessions, the p-value fluctuated between 0.03, 0.20, and 0.05. Had the test been stopped when p first crossed 0.05, the conclusion would have been based on noise. This is the peeking problem, and it is a real operational risk when teams check significance daily.

**The Bayesian probability of superiority converged smoothly.**

The Bayesian metric identified the winner at N = 2,000 sessions — before the p-value stabilized — and did not reverse as more data arrived. It gave a stable, interpretable signal earlier.

---

## Why This Matters

A frequentist test answers: "Is this result statistically significant?"

A Bayesian test answers: "What is the probability that this decision is correct?"

For business decisions made under time pressure, the second question is more useful. A 98% probability of superiority is a number a product manager can act on.
---

## Methodology

**Data:** Synthetic dataset of 5,100 user sessions, simulating realistic e-commerce logs with bots, duplicates, and missing values included and cleaned.

**Frequentist approach:**
- Pearson's Chi-Squared test for conversion rate differences.
- Mann-Whitney U test for revenue per user distributions (non-normal data).

**Bayesian approach:**
- Beta-Binomial conjugate model.
- Weakly informative prior: Beta(2, 98), reflecting a realistic baseline conversion rate.
- Prior updated sequentially as sessions accumulated.
- Final posterior used to calculate probability of superiority.

**Sensitivity analysis:** Tested multiple prior specifications to confirm the result is not fragile to the choice of starting assumptions. The 98.4% posterior held across all reasonable priors.

---

## Limitations

- Synthetic data. The findings demonstrate methodology but do not reflect a real business outcome.
- Results apply to this product density context. Different industries and page types may not follow the same pattern.

---

## Tools

Python, NumPy, SciPy, Matplotlib, Bayesian Beta-Binomial model, Monte Carlo simulation
