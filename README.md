# 📊 A/B Testing Statistics Cheat Sheet

A high-impact guide to core statistical concepts every data scientist should know for designing, analyzing, and interpreting A/B tests. Perfect for interviews, real-world applications, or quick refreshers.

---

## 🧠 1. Central Limit Theorem (CLT)
**What It Means:**
- The sampling distribution of the **sample mean** becomes approximately **normal** as the sample size increases, regardless of the population’s distribution.

**Why It Matters in A/B Testing:**
- Allows use of **z-tests and confidence intervals** even when raw data is skewed (like binary conversions).

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

**Real-World Relevance:**
- Underpowered studies can lead to costly missed opportunities or false negatives in product decisions.

---

## 📈 5. Population vs Estimated Parameters
**Population Parameter:**
- The **true** value we aim to estimate (e.g., true conversion rate of all users)

**Sample Estimate (Statistic):**
- The value we calculate from a subset (e.g., sample conversion rate)

**In A/B Testing:**
- We observe a sample (e.g., 5% conversion rate in group A) and infer what that means for the population.

---

## 🧮 6. Power Analysis
**What It Does:**
- Estimates one of four key factors — sample size, effect size, significance level, or statistical power — given the other three.

**Used For:**
- Planning experiments to ensure results are statistically meaningful and not due to chance.

**Four Interconnected Components:**
- **Effect Size:** Magnitude of the observed difference.
- **Sample Size:** Number of observations needed.
- **Significance Level (α):** Threshold for p-value (commonly 0.05).
- **Power (1 - β):** Probability of detecting a true effect (commonly set to 0.8).

**A Priori vs Post-Hoc:**
- **A Priori Power Analysis:** Done before the experiment to determine necessary sample size.
- **Post-Hoc Power Analysis:** Done after, but can be misleading — not recommended.

**Practical Considerations:**
- **Simple Sampling:** Assumes Gaussian distribution; stratified samples need adjustments.
- **Appropriate Size by Test Type:** Complex models (e.g., ANOVA, regression) need larger samples.
- **Buffer for Dropouts/Errors:** Add ~25% to account for unusable data or noncompliance.

**Business Applications:**
- Helps teams avoid over-testing (wasting resources) or under-testing (missing effects).
- Used by R&D teams, UX researchers, and product analysts to plan impactful, efficient experiments.

**Example:**
- A streaming platform tests a new recommendation algorithm. Power analysis shows 8,000 users are needed per variant to detect a 2% uplift in click-through rate.

**Common Pitfalls:**
- Bigger sample sizes may detect **tiny, unimportant effects**.
- Focus on power can overshadow **confidence intervals and practical significance**.
- Retrospective power analysis offers **no real insight** into study validity.

**Alternatives:**
- **Meta-Experimentation:** Multiple small studies can offer reliable insights.
- **Monte Carlo Simulations:** Use computational methods to simulate different outcomes and estimate power dynamically.

---

✨ Prepared by **Bhavya Samhitha Mallineni** 
