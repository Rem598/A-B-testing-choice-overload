## Bayesian A/B Testing: The Paradox of Choice 

A statistical experiment comparing Frequentist and Bayesian in the context of Hick's Law.

## 📌 Overview

This project investigates Hick's Law (Choice Overload) in an e-commerce context. The hypothesis: Does reducing product density on category pages (from 24 items to 6 items) reduce cognitive load and improve conversion rates?

Beyond the business question, this project serves as a methodological comparison between:

- Frequentist Inference: Chi-Square tests and p-values.

- Bayesian Inference: Beta-Binomial conjugate models.

---
## 🔍 Key Findings

Using a synthetic dataset of 5,100 user sessions (simulating a scenario with noisy data), the analysis revealed:

- The Peeking Problem: The Frequentist p-value fluctuated significantly ($p \approx 0.03 \to 0.20 \to 0.05$) as data accumulated, posing a risk of Type I errors if the test were stopped early.

- Bayesian Stability: The Bayesian probability of superiority ($P(B>A)$) converged smoothly, identifying the winner at $N=2,000$ users—long before the p-value stabilized.

Final Result: The Low Density layout achieved a 98.4% Probability of Superiority and a ~40% lift in Revenue per User.

---

## 🛠️ Methodology

1. Data Engineering

Simulated realistic, messy e-commerce logs including:

- Bots & Duplicates

- Missing Data: Null values.



2. Statistical Models

- Frequentist: Pearson's Chi-Squared Test ($\chi^2$) for conversion rates; Mann-Whitney U Test for revenue distributions.

- Bayesian: Beta-Binomial model ($\alpha, \beta$) updating a weakly informative prior Beta(2, 98) to calculate Posterior probabilities.



---


