# 📊 A/B Testing Statistics 

A high-impact guide to core statistical concepts every data scientist should know for designing, analyzing, and interpreting A/B tests.

---

## 🧠 1. Central Limit Theorem (CLT)

**What It Means:**

- The sampling distribution of the **sample mean** becomes approximately **normal** as the sample size increases, regardless of the population’s distribution.

**Why It Matters in A/B Testing:**

- Allows use of **z-tests and confidence intervals** even when raw data is skewed (like binary conversions).

**Key Point:**

- With n ≥ 30, the average metric (e.g., conversion rate) becomes normally distributed, enabling statistical inference.

**Real-Life Example:**

- Even though individual users either convert (1) or not (0), the average conversion rate of 1000 users will be normally distributed.

---

## 🎯 2. P-Value

**What It Means:**

- The probability of observing the given result (or more extreme) **assuming the null hypothesis is true**.

**Misconception:**

- P-value is **not** the probability that the null hypothesis is true.

**In Practice:**

- If **p < α (e.g., 0.05)**, we reject the null hypothesis — indicating a statistically significant result.

**Example:**

- In a test between two product pages, p = 0.03 means there’s a 3% chance you’d see this difference if there were **no true difference**.

---

## ⚠️ 3. P-Hacking

**What It Is:**

- Manipulating experiments or analyses until statistically significant results are found.

**Examples:**

- Peeking at the data early
- Running multiple versions without correction
- Selectively reporting results

**Why It’s Dangerous:**

- Increases risk of **false positives (Type I error)**

**Best Practices:**

- Predefine hypothesis, sample size, analysis method
- Use corrections like **Bonferroni** for multiple comparisons

---

## 🔍 4. Statistical Power

**What It Means:**

- The probability of **correctly detecting a true effect** (i.e., rejecting a false null hypothesis)

**Power = 1 - β**, where **β = probability of Type II error**

**Why It Matters:**

- High power (≥ 80%) ensures you don’t miss a real effect due to small sample size or noisy data.

**Boosting Power:**

- Increase sample size
- Detect larger effects
- Reduce data variability

**Example:**

- If the new signup flow actually improves conversion, but your test is underpowered, you might miss it — wasting a real opportunity.

---

## 📈 5. Population vs Estimated Parameters

**Population Parameter:**

- The **true** value we aim to estimate (e.g., true conversion rate of all users)

**Sample Estimate (Statistic):**

- The value we calculate from a subset (e.g., sample conversion rate)

**In A/B Testing:**

- We observe a sample (e.g., 5% conversion rate in group A) and infer what that means for the population.

**Key Point:**

- All test results (means, proportions) are **approximations** — that’s why we use **confidence intervals** and hypothesis tests.

---

## 🧮 6. Power Analysis

**What It Does:**

- Determines **how many samples you need** to reliably detect a given effect size

**Key Inputs:**

- Baseline conversion rate
- Minimum detectable effect (MDE)
- Significance level (α)
- Desired power (e.g., 80%)

**Why It Matters:**

- Helps balance speed and accuracy in experimentation.
- Prevents inconclusive tests (too small) or wasted resources (too large).

**Example:**

- Want to detect a 2% lift from a 10% baseline? A power analysis might suggest 12,000 users per variant for 80% power.

