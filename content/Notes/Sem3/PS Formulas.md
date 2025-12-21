---
title: PS Formulas
draft: false
tags:
---
> * [[Notes/Sem3/index|index]]
---

# [[Notes/Sem3/Probability and Statistics | PS Theory]]
---

### **Unit 1: Basic Probability Theory**

- **Classical Probability:** $P(A) = \frac{\text{favorable outcomes}}{\text{total outcomes}} = \frac{m}{n}$.
- **Complementation Rule:** $P(A') = 1 - P(A)$.
- **Addition Rules (Union of Events):**
    - For two events: $P(A \cup B) = P(A) + P(B) - P(A \cap B)$.
    - For three events: $P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(B \cap C) - P(C \cap A) + P(A \cap B \cap C)$.
- **De Morgan’s Rules (Probability Form):**
    - $P(A' \cap B') = P(A \cup B)' = 1 - P(A \cup B)$.
    - $P(A' \cup B') = P(A \cap B)' = 1 - P(A \cap B)$.
- **Counting Formulas:**
    - **Permutations:** $P^n_r = \frac{n!}{(n - r)!}$.
    - **Permutations with Identical Objects:** $\frac{n!}{n_1! n_2! \dots n_k!}$.
    - **Combinations:** $^nC_r = \binom{n}{r} = \frac{n!}{r! (n - r)!}$.
- **Conditional Probability:** $P(A | B) = \frac{P(A \cap B)}{P(B)}$ (where $P(B) > 0$).
- **Multiplication Rules:**
    - For two events: $P(A \cap B) = P(A) \cdot P(B | A)$.
    - For three events: $P(A \cap B \cap C) = P(A) \cdot P(B | A) \cdot P(C | A \cap B)$.
- **Independent Events:** $P(A \cap B) = P(A) \cdot P(B)$.
- **Total Probability:** $P(A) = P(B_1) \cdot P(A | B_1) + P(B_2) \cdot P(A | B_2) + \dots$.
- **Bayes’ Theorem:** $P(B_i | A) = \frac{P(B_i) \cdot P(A | B_i)}{\sum_{j=1}^n P(B_j) \cdot P(A | B_j)}$.
- **Mathematical Expectation:**
    - **Discrete:** $E(X) = \sum_{i=1}^n x_i \cdot P(x_i)$.
    - **Continuous:** $E(X) = \int_{-\infty}^{\infty} x f(x) dx$.
- **Variance and Standard Deviation:**
    - **Variance:** $V(X) = E(X^2) - [E(X)]^2$.
    - **Standard Deviation:** $\sigma = \sqrt{V(X)}$.
- **Joint and Marginal Distributions:**
    - **Marginal Probability (Discrete):** $P_X(x) = \sum_y P(X=x, Y=y)$.
    - **Marginal Density (Continuous):** $f_X(x) = \int_{-\infty}^{\infty} f(x, y) dy$.
    - **Conditional Density:** $f(y | x) = \frac{f(x, y)}{f_X(x)}$.

### **Unit 2: Special Probability Distributions**

- **Binomial Distribution:**
    - **Probability Mass Function (PMF):** $P(X = x) = \binom{n}{x} p^x q^{n-x}$.
    - **Mean:** $\mu = np$; **Variance:** $V(X) = npq$.
- **Poisson Distribution:**
    - **PMF:** $P(X = x) = \frac{e^{-\lambda} \lambda^x}{x!}$.
    - **Mean and Variance:** $\mu = V(X) = \lambda = np$.
- **Exponential Distribution:**
    - **Probability Density Function (PDF):** $f(x) = \theta e^{-\theta x}$ (for $x \geq 0$).
    - **Mean:** $1/\theta$; **Variance:** $1/\theta^2$.
- **Gamma Distribution:**
    - **PDF:** $f(x) = \frac{\theta^r x^{r-1} e^{-\theta x}}{\Gamma(r)}$.
    - **Mean:** $r/\theta$; **Variance:** $r/\theta^2$.
- **Normal Distribution:**
    - **PDF:** $f(x) = \frac{1}{\sigma \sqrt{2\pi}} \exp\left[-\frac{1}{2}\left(\frac{x - \mu}{\sigma}\right)^2\right]$.
    - **Standard Normal Variable (Z-score):** $Z = \frac{X - \mu}{\sigma}$.
- **Chebyshev’s Inequality:** $P(|X - \mu| \geq k\sigma) \leq 1/k^2$.

### **Unit 3: Basic Statistics**

- **Arithmetic Mean ($\bar{x}$):**
    - **Ungrouped:** $\bar{x} = \frac{\sum x_i}{n}$.
    - **Step Deviation Method:** $\bar{x} = A + \left(\frac{\sum f_i u_i}{n}\right) \cdot C$.
- **Median (M):**
    - **Continuous Grouped Data:** $M = L + \left(\frac{n/2 - F}{f}\right) \times C$.
- **Mode (Z):**
    - **Continuous Grouped Data:** $Z = L + \left(\frac{f_1 - f_0}{2f_1 - f_0 - f_2}\right) \times C$.
    - **Empirical Relation:** $Z = 3 \cdot \text{Median} - 2 \cdot \text{Mean}$.
- **Dispersion:**
    - **Coefficient of Variation:** $C.V. = \frac{\sigma}{\bar{x}} \times 100$.
    - **Mean Deviation (M.D.):** $M.D. = \frac{\sum f_i |x_i - \bar{x}|}{n}$.
- **Moments:**
    - **$r$-th Central Moment ($\mu_r$):** $\mu_r = \frac{\sum f_i (x - \bar{x})^r}{n}$.
    - **Relationship between central and raw moments:** $\mu_2 = \mu'_2 - (\mu'_1)^2$.
- **Skewness and Kurtosis:**
    - **Moment Coefficient of Skewness:** $\beta_1 = \frac{\mu_3^2}{\mu_2^3}$.
    - **Moment Coefficient of Kurtosis:** $\beta_2 = \frac{\mu_4}{\mu_2^2}$.
- **Correlation and Regression:**
    - **Karl Pearson’s Correlation Coefficient ($r$):** $r = \frac{n \sum xy - (\sum x)(\sum y)}{\sqrt{n \sum x^2 - (\sum x)^2} \sqrt{n \sum y^2 - (\sum y)^2}}$.
    - **Spearman’s Rank Correlation ($\rho$):** $\rho = 1 - \frac{6 \sum d^2}{n(n^2 - 1)}$.
    - **Regression Coefficient ($y$ on $x$):** $b_{yx} = r \frac{\sigma_y}{\sigma_x}$.
    - **Regression Line ($y$ on $x$):** $y - \bar{y} = b_{yx}(x - \bar{x})$.

### **Unit 4: Applied Statistics**

- **Standard Error (S.E.) and Z-Test:** $z = \frac{t - E(t)}{S.E.(t)}$.
- **Test for Single Proportion:** $z = \frac{p - P}{\sqrt{PQ/n}}$.
- **Test for Difference of Proportions:** $z = \frac{p_1 - p_2}{\sqrt{PQ(\frac{1}{n_1} + \frac{1}{n_2})}}$.
- **t-Test for Small Samples ($n < 30$):**
    - **Single Mean:** $t = \frac{\bar{x} - \mu}{s/\sqrt{n}}$ where $s^2 = \frac{\sum(x_i - \bar{x})^2}{n-1}$.
    - **Difference of Means:** $t = \frac{\bar{x} - \bar{y}}{\sigma \sqrt{\frac{1}{n_1} + \frac{1}{n_2}}}$.
- **F-Test for Ratio of Variances:** $F = \frac{s_1^2}{s_2^2}$.
- **Chi-Square ($\chi^2$) Test:**
    - **Goodness of Fit:** $\chi^2 = \sum \frac{(o_i - e_i)^2}{e_i}$.
    - **Independence of Attributes:** $\chi^2 = \sum \frac{(O_{ij} - E_{ij})^2}{E_{ij}}$ with degrees of freedom $v = (r - 1)(c - 1)$.

### **Unit 5: Curve Fitting**

- **Least Square Error:** $D = \sum [y_i - f(x_i)]^2$.
- **Normal Equations for a Straight Line ($y = a + bx$):**
    - $\sum y = an + b \sum x$.
    - $\sum xy = a \sum x + b \sum x^2$.
- **Normal Equations for a Parabola ($y = a + bx + cx^2$):**
    - $\sum y = na + b \sum x + c \sum x^2$.
    - $\sum xy = a \sum x + b \sum x^2 + c \sum x^3$.
    - $\sum x^2y = a \sum x^2 + b \sum x^3 + c \sum x^4$.

To visualize these concepts, imagine **statistics as a toolbox** where each formula is a specialized tool; just as you wouldn't use a hammer to tighten a screw, you choose a **t-test** for small samples and a **z-test** for large ones to ensure the most accurate "fit" for your data.