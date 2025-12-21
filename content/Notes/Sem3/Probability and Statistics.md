---
title: Probability and Statistics
draft: false
tags:
---
> * [[Notes/Sem3/index|index]]
---
# Formulas => [[PS Formulas]]
---

## Executive Summary

**Unit 1: Basic Probability Theory** establishes the core principles, including sample spaces, events, conditional probability, and Bayes' theorem. It introduces random variables, distinguishing between discrete and continuous types, and details the calculation of mathematical expectation and variance. The unit concludes with an examination of two-dimensional random variables and joint probability functions.

**Unit 2: Special Probability Distributions** delves into key discrete and continuous probability distributions used in statistical analysis. It details the properties, formulas (PMF/PDF), and applications of the Binomial, Poisson, Exponential, Gamma, and Normal distributions. The unit also introduces Chebyshev's Inequality as a tool for creating bounds on probabilities.

**Unit 3: Basic Statistics** focuses on descriptive statistics and the analysis of relationships between variables. It covers measures of central tendency (Mean, Median, Mode), measures of dispersion (Standard Deviation, Variance), and higher-order concepts such as Moments, Skewness, and Kurtosis. The latter half of the unit is dedicated to Correlation and Regression analysis, providing methods to quantify the relationship and model dependencies between two variables.

**Unit 4: Applied Statistics** transitions to inferential statistics, centering on hypothesis testing. It outlines the foundational concepts of sampling, null and alternative hypotheses, and statistical significance. The unit provides detailed frameworks for conducting both large-sample tests (z-tests for proportions and means) and small-sample tests (t-tests for means).

**Unit 5: Curve Fitting by Numerical Method** outlines techniques for modeling data by fitting it to mathematical functions. The methods specified include fitting data to a straight line, a parabola, and other general curves.

## Unit 1: Basic Probability Theory

This unit lays the groundwork for understanding probability, defining its core components and mathematical rules.

### Foundational Concepts

- **Probability Theory:** Defined as the branch of mathematics concerned with random (or chance) phenomena, with applications in physical, biological, social sciences, engineering, and business. The theory is presented through two main approaches: the Classical Approach (by Blaise Pascal) and the Axiomatic Approach (by A. Kolmogorov).
- **Random Experiment:** An experiment whose outcome cannot be successfully predicted in advance, although all possible outcomes are known.
- **Sample Space (S):** The set of all possible outcomes of a random experiment. It can be finite (e.g., tossing a coin twice, S = {HH, HT, TH, TT}) or infinite (e.g., tossing a coin until a head appears, S = {H, TH, TTH, ...}).
- **Event:** A subset of a sample space. Key types of events include:
    - **Impossible Event (∅):** An empty subset.
    - **Sure/Certain Event (S):** The entire sample space.
    - **Elementary/Simple Event:** A subset containing only one element.
    - **Compound Event:** A subset containing more than one element.
    - **Complementary Event (A'):** The set of all elements not in event A.
    - **Mutually Exclusive Events:** Two events A and B where their intersection is empty (A ∩ B = ∅).
    - **Mutually Exhaustive Events:** Two events A and B where their union is the entire sample space (A ∪ B = S).

### Probability Calculation and Rules

- **Probability of an Event P(A):** Defined as the ratio of favorable outcomes (m) to the total number of equally likely outcomes (n). `P(A) = m / n`
- **Key Results:**
    - For any event A, `0 ≤ P(A) ≤ 1`.
    - `P(∅) = 0`.
    - Complementation Rule: `P(A′) = 1 − P(A)`.
    - Addition Rule: `P(A ∪ B) = P(A) + P(B) − P(A ∩ B)`.
    - De Morgan’s Rules: `P(A′ ∩ B′) = 1 − P(A ∪ B)` and `P(A′ ∪ B′) = 1 − P(A ∩ B)`.

### Permutations and Combinations

- **Permutation (**`**nPr**`**):** An arrangement of 'r' objects selected from 'n' distinct objects where order matters. `nPr = n! / (n − r)!`
- **Combination (**`**nCr**`**):** A selection of 'r' objects from 'n' objects where order does not matter. `nCr = n! / (r! * (n − r)!)`

### Conditional Probability and Independence

- **Conditional Probability (P(A|B)):** The probability of event A occurring given that event B has already occurred. `P(A|B) = P(A ∩ B) / P(B)`, where `P(B) > 0`.
- **Multiplication Rule:** `P(A ∩ B) = P(A) * P(B|A)`.
- **Independent Events:** Two events A and B are independent if the occurrence of one does not affect the probability of the other. This holds if `P(A ∩ B) = P(A) * P(B)`.

### Total Probability and Bayes' Theorem

- **Total Probability:** If B1, B2, ..., Bn are mutually exclusive and exhaustive events, the probability of any event A is given by: `P(A) = Σ P(Bi) * P(A|Bi)`
- **Bayes' Theorem:** Provides a way to update the probability of a hypothesis based on new evidence. It calculates the probability of an event Bi, given that event A has occurred. `P(Bi|A) = (P(Bi) * P(A|Bi)) / Σ P(Bj) * P(A|Bj)`

### Random Variables

- **Random Variable (X):** A function that assigns a numerical value to each outcome of an experiment.
    - **Discrete Random Variable:** Can take on a finite or countably infinite number of specific values.
    - **Continuous Random Variable:** Can take on any value within a continuous range.
- **Probability Distribution:** A set of all possible values of a random variable along with their respective probabilities.
    - **Probability Mass Function (PMF), p(x):** For discrete variables. `p(xi) ≥ 0` and `Σp(xi) = 1`.
    - **Probability Density Function (PDF), f(x):** For continuous variables. `f(x) ≥ 0` and `∫f(x)dx = 1`.

### Mathematical Expectation and Variance

- **Mathematical Expectation (E(X) or μ):** The mean or average value of a random variable.
    - Discrete: `E(X) = Σ xi * p(xi)`
    - Continuous: `E(X) = ∫ x * f(x) dx`
- **Variance (V(X) or σ²):** A measure of the dispersion or spread of a random variable around its mean. `V(X) = E(X²) - [E(X)]²`
- **Standard Deviation (σ):** The positive square root of the variance, `σ = √V(X)`.

### Two-Dimensional Random Variables

- **Two-Dimensional Random Variable (X, Y):** A function that assigns a pair of real numbers to each outcome in a sample space.
- **Joint Probability Function:**
    - **Discrete (pij):** `pij = P(X = xi, Y = yj)`. Requires `pij ≥ 0` and `ΣΣpij = 1`.
    - **Continuous (f(x, y)):** A function where `f(x, y) ≥ 0` and `∬f(x, y)dxdy = 1`.
- **Marginal Probability Function:** The probability distribution of a single variable in a multi-variable system.
    - Discrete: `PX(x) = Σy P(X=x, Y=y)`
    - Continuous: `FX(x) = ∫ f(x, y)dy`
- **Independent Random Variables:** Two variables X and Y are independent if their joint probability function is the product of their marginal probability functions (`f(x, y) = FX(x) * FY(y)`).

## Unit 2: Special Probability Distributions

This unit examines several widely used theoretical probability distributions, detailing their mathematical definitions, parameters, and common applications.

### Binomial Distribution

- **Description:** Models the number of successes in a fixed number of independent Bernoulli trials.
- **Conditions:**
    1. `n` independent trials.
    2. Each trial has only two outcomes: success or failure.
    3. The probability of success, `p`, is constant for each trial.
- **Probability Mass Function (PMF):** `P(X = x) = (nCx) * p^x * q^(n-x)`, where `q = 1-p`.
- **Parameters:**
    - Mean (μ): `np`
    - Variance (σ²): `npq`

### Poisson Distribution

- **Description:** Models the number of times an event occurs in a fixed interval of time or space, particularly for rare events.
- **Conditions:**
    1. The number of trials `n` is very large.
    2. The probability of success `p` is very small.
    3. Occurrences are rare and independent.
- **Probability Mass Function (PMF):** `P(X = x) = (e^(-λ) * λ^x) / x!`, where `λ = np`.
- **Parameters:**
    - Mean (μ): `λ`
    - Variance (σ²): `λ`

### Exponential Distribution

- **Description:** A continuous distribution used to model the time until an event occurs, such as waiting times or lifespans. It is a special case of the Gamma distribution.
- **Probability Density Function (PDF):** `f(x) = θ * e^(-θx)` for `x ≥ 0`.
- **Parameters:**
    - Mean (μ): `1/θ`
    - Variance (σ²): `1/θ²`

### Gamma Distribution

- **Description:** A continuous distribution that generalizes the Exponential distribution, often used to model waiting times until a specified number of events occur.
- **Probability Density Function (PDF):** `f(x) = (θ^r * x^(r-1) * e^(-θx)) / Γ(r)` for `x ≥ 0`.
- **Parameters:**
    - Mean (μ): `r/θ`
    - Variance (σ²): `r/θ²`

### Normal Distribution

- **Description:** A continuous, symmetric, bell-shaped distribution that is fundamental to statistics.
- **Probability Density Function (PDF):** `f(x) = (1 / (σ * √2π)) * exp[ -0.5 * ((x - μ) / σ)² ]`.
- **Standard Normal Variable (Z):** A transformation `Z = (X - μ) / σ` results in a normal distribution with a mean of 0 and a standard deviation of 1.
- **Parameters:**
    - Mean (μ)
    - Standard Deviation (σ)

### Chebyshev's Inequality

- **Description:** Provides an upper bound on the probability that a random variable falls a certain distance from its mean, regardless of the variable's specific distribution.
- **Formula:** `P(|X - μ| ≥ kσ) ≤ 1/k²` or `P(|X - μ| < kσ) ≥ 1 - 1/k²`.

## Unit 3: Basic Statistics

This unit covers methods for summarizing, analyzing, and interpreting data, including measures of central tendency, dispersion, shape, and relationships between variables.

### Measures of Central Tendency

- **Mean (x̅):** The arithmetic average of a dataset.
    - Ungrouped Data: `x̅ = (Σ xi) / n`
    - Grouped Data: `x̅ = (Σ fixi) / n`
- **Median (M):** The middle value in an ordered dataset.
    - Continuous Grouped Data: `M = L + ( (n/2 - F) / f ) * C`
- **Mode (Z):** The most frequently occurring value in a dataset.
    - Continuous Grouped Data: `Z = L + ( (f1 - f0) / (2f1 - f0 - f2) ) * C`

### Measures of Dispersion

- **Range:** The difference between the highest and lowest values.
- **Variance (σ²):** The average of the squared deviations from the mean.
- **Standard Deviation (σ):** The square root of the variance, quantifying the amount of variation.
- **Coefficient of Variation (C.V.):** A relative measure of dispersion, used for comparing variability between datasets. `C.V. = (σ / x̅) * 100`

### Moments, Skewness, and Kurtosis

- **Moments:** A set of statistical parameters to measure a distribution. Central moments (`μr`) are moments about the mean. `μ2` is the variance.
- **Skewness (β1):** A measure of the asymmetry of a probability distribution.
    - `β1 = (μ3)² / (μ2)³`
    - **Positive Skew:** Right tail is longer.
    - **Negative Skew:** Left tail is longer.
    - **Zero Skew:** Symmetric distribution.
- **Kurtosis (β2):** A measure of the "peakedness" or "tailedness" of a distribution.
    - `β2 = μ4 / (μ2)²`
    - **Leptokurtic (β2 > 3):** More peaked than a normal distribution.
    - **Mesokurtic (β2 = 3):** Normal peakedness (like a normal distribution).
    - **Platykurtic (β2 < 3):** Flatter than a normal distribution.

### Correlation and Regression

- **Correlation:** Measures the strength and direction of a linear relationship between two variables. The coefficient `r` ranges from -1 (perfect negative correlation) to +1 (perfect positive correlation), with 0 indicating no linear correlation.
    - **Karl Pearson's Coefficient (r):** `r = (nΣxy - (Σx)(Σy)) / (√[nΣx² - (Σx)²] * √[nΣy² - (Σy)²])`
    - **Spearman's Rank Coefficient (ρ):** Used for ranked data. `ρ = 1 - (6Σd²) / (n(n² - 1))`.
- **Regression Analysis:** Formulates an algebraic equation to model the relationship between variables.
    - **Regression Line of y on x:** `y - y̅ = byx * (x - x̅)`, where `byx` is the regression coefficient `r * (σy / σx)`.
    - **Regression Line of x on y:** `x - x̅ = bxy * (y - y̅)`, where `bxy` is the regression coefficient `r * (σx / σy)`.
- **Properties of Regression Coefficients:** The geometric mean of the regression coefficients is the correlation coefficient: `r = √byx * bxy`.

## Unit 4: Applied Statistics

This unit focuses on statistical inference through hypothesis testing, providing procedures to make decisions about population parameters based on sample data.

### Core Concepts of Hypothesis Testing

- **Population vs. Sample:** A population is the entire group under study, while a sample is a subset of the population used for analysis.
- **Null Hypothesis (H0):** A default statement that there is no effect or no difference, which the test aims to challenge. It is always a statement of equality.
- **Alternative Hypothesis (H1):** The statement that contradicts the null hypothesis (e.g., an effect or difference exists). It can be two-tailed (`≠`), right-tailed (`>`), or left-tailed (`<`).
- **Test of Significance:** A procedure to decide whether to reject the null hypothesis based on sample evidence.
- **Errors in Sampling:**
    - **Type I Error (α):** Rejecting H0 when it is true.
    - **Type II Error (β):** Failing to reject H0 when it is false.
- **Standard Error:** The standard deviation of a sampling distribution of a statistic.
- **General Steps for Testing:**
    1. State the Null Hypothesis (H0).
    2. State the Alternative Hypothesis (H1).
    3. Set the Level of Significance (α).
    4. Determine the Critical Region.
    5. Compute the Test Statistic (e.g., `z` or `t`).
    6. Make a Conclusion: Reject H0 if the test statistic falls in the critical region; otherwise, do not reject H0.

### Large Sample Tests (n ≥ 30)

|   |   |   |
|---|---|---|
|Test Type|Null Hypothesis (H0)|Test Statistic Formula|
|**Test for Single Proportion**|`P = P0`|`z = (p - P) / √(PQ/n)`|
|**Test for Difference between Proportions**|`P1 = P2`|`z = (p1 - p2) / √[PQ(1/n1 + 1/n2)]`, where `P = (n1p1 + n2p2)/(n1+n2)`|
|**Test for Single Mean**|`μ = μ0`|`z = (x̅ - μ) / (σ/√n)` (if σ is known) or `z = (x̅ - μ) / (s/√n)` (if σ is unknown)|
|**Test for Difference between Means**|`μ1 = μ2`|`z = (x̅1 - x̅2) / √[(s1²/n1) + (s2²/n2)]`|
|**Test for Difference between Standard Deviations**|`σ1 = σ2`|`z = (s1 - s2) / √[(s1²/2n1) + (s2²/2n2)]`|

### Small Sample Tests (n < 30)

|   |   |   |
|---|---|---|
|Test Type|Null Hypothesis (H0)|Test Statistic Formula|
|**t-test for Single Mean**|`μ = μ0`|`t = (x̅ - μ) / (s/√n)`, where `s² = Σ(xi - x̅)² / (n-1)`|
|**t-test for Difference between Means**|`μ1 = μ2`|`t = (x̅ - y̅) / [σ * √(1/n1 + 1/n2)]`, where `σ² = [(n1-1)s1² + (n2-1)s2²] / (n1+n2-2)`|

## Unit 5: Curve Fitting by Numerical Method

This unit addresses the process of constructing a mathematical function that best fits a series of data points. The objective is to model the underlying relationship between variables. The material covers the following primary methods:

- **Method 1: Fitting a Straight Line:** Finding the best linear equation (`y = a + bx`) to represent the data, typically using the method of least squares.
- **Method 2: Fitting a Parabola:** Modeling data with a second-degree polynomial (`y = a + bx + cx²`).
- **Method 3: Fitting General Curves:** Applying techniques to fit data to other non-linear functions.