---
title: Statistics Cheatsheet
date: April 20, 2026 11:07 AM
categories:
  - stat
tags:
  - data
  - data-analysis
  - stat
  - EDA
  - google
description: This is a cheatsheet for quick reference and knowledge refresh
  after Google's The Power of Statistics course.
toc: true
comments: true
math: true
image: ""
---
# Descriptive Statistics

Descriptive statistics summarize and describe the main features of a dataset. They help us understand what the data looks like without making predictions.

## Mean

The mean is the average of all values in a dataset. Add up all numbers and divide by how many numbers there are.

**Formula:**

$$\bar{x} = \frac{\sum_{i=1}^{n} x_i}{n}$$

**What this means:**
- $\bar{x}$ (x-bar) = the mean
- $\sum$ (sigma) = add up everything that comes after
- $x_i$ = each individual value in your dataset
- $n$ = how many values you have total

So you're adding up all your values and dividing by the count.

**When to use:** When you want a typical value and your data doesn't have extreme outliers.

**Example:** For [2, 4, 6, 8, 10], the mean is $(2+4+6+8+10)/5 = 30/5 = 6$

## Median

The median is the middle value when data is arranged in order. If there's an even number of values, it's the average of the two middle numbers.

**When to use:** When your data has outliers or is skewed, since the median isn't affected by extreme values.

**Example:** For [2, 4, 6, 8, 100], the median is 6 (not affected by the outlier 100)

## Mode

The mode is the value that appears most frequently in a dataset. A dataset can have no mode, one mode, or multiple modes.

**When to use:** For categorical data or when you want to know the most common value.

**Example:** For [1, 2, 2, 3, 4, 4, 4, 5], the mode is 4

## Variance and Standard Deviation

**Variance** measures how spread out the data is from the mean. It's the average of squared differences from the mean.

**Population Variance:**

$$\sigma^2 = \frac{\sum_{i=1}^{n} (x_i - \mu)^2}{n}$$

**What this means:**
- $\sigma^2$ (sigma squared) = population variance
- $x_i$ = each individual value
- $\mu$ (mu) = population mean
- $(x_i - \mu)$ = how far each value is from the mean
- $(x_i - \mu)^2$ = that distance squared (makes everything positive)
- Divide by $n$ to get the average

**Sample Variance:**

$$s^2 = \frac{\sum_{i=1}^{n} (x_i - \bar{x})^2}{n-1}$$

**What this means:**
- $s^2$ = sample variance
- $\bar{x}$ = sample mean
- We divide by $n-1$ instead of $n$ (this corrects for bias when estimating from a sample)

**Standard Deviation** is the square root of variance. It tells you the typical distance between data points and the mean, in the same units as your data.

**Population Standard Deviation:**

$$\sigma = \sqrt{\frac{\sum_{i=1}^{n} (x_i - \mu)^2}{n}}$$

**Sample Standard Deviation:**

$$s = \sqrt{\frac{\sum_{i=1}^{n} (x_i - \bar{x})^2}{n-1}}$$

**What this means:**
- Just take the square root of variance
- This converts back to the original units (if variance is in "dollars squared", standard deviation is in "dollars")

**Why it matters:** Low standard deviation means data points are close to the mean. High standard deviation means they're spread out.

## Range and Quartiles

**Range:** The difference between the maximum and minimum values.

$$\text{Range} = \max(x) - \min(x)$$

**Quartiles:** Divide your ordered data into four equal parts. Q1 (25th percentile), Q2 (median), Q3 (75th percentile).

**IQR (Interquartile Range):** 

$$\text{IQR} = Q_3 - Q_1$$

**What this means:**
- $Q_3$ = the value at the 75th percentile
- $Q_1$ = the value at the 25th percentile
- IQR represents the middle 50% of your data

# Inferential Statistics

Inferential statistics use sample data to make predictions or inferences about a larger population.

## Population vs Sample

**Population:** The entire group you want to study.

**Sample:** A subset of the population that you actually collect data from.

**Why sampling:** Usually impossible or impractical to measure an entire population.

## Sampling Methods

**Random sampling:** Every member has an equal chance of being selected.

**Stratified sampling:** Divide population into groups (strata) and sample from each.

**Systematic sampling:** Select every nth member.

**Convenience sampling:** Use whatever's easily available (often biased).

## Point Estimation

A single value estimate of a population parameter based on sample data.

**Example:** Using sample mean $\bar{x}$ to estimate population mean $\mu$.

**Problem:** Doesn't tell you how confident you should be in that estimate.

## Standard Error

The standard error tells you how much your sample statistic (like the mean) would vary if you took many different samples.

**Standard Error of the Mean:**

$$SE = \frac{s}{\sqrt{n}}$$

**What this means:**
- $SE$ = standard error
- $s$ = sample standard deviation
- $n$ = sample size
- $\sqrt{n}$ = square root of sample size
- Larger samples give smaller standard errors (more precise estimates)

## Z-Scores and T-Scores

These are standardized scores that tell you how many standard deviations away from the mean a value is.

### Z-Score

**Formula:**

$$z = \frac{x - \mu}{\sigma}$$

**What this means:**
- $z$ = z-score (standardized score)
- $x$ = your data point
- $\mu$ = population mean
- $\sigma$ = population standard deviation
- Tells you how many standard deviations $x$ is from the mean

**Example:** If $\mu = 100$, $\sigma = 15$, and $x = 130$, then $z = (130-100)/15 = 2$. This means 130 is 2 standard deviations above the mean.

**For sample data:**

$$z = \frac{\bar{x} - \mu}{\sigma / \sqrt{n}}$$

**What this means:**
- $\bar{x}$ = sample mean
- $\sigma / \sqrt{n}$ = standard error (using population standard deviation)
- Used when you know the population standard deviation

### T-Score

**Formula:**

$$t = \frac{\bar{x} - \mu}{s / \sqrt{n}}$$

**What this means:**
- $t$ = t-score
- $s$ = sample standard deviation (not population)
- Everything else same as z-score
- Used when you DON'T know the population standard deviation (most real-world cases)

### Why Z-Scores and T-Scores Matter

**1. Standardization:** They let you compare apples to oranges.
- Is a score of 85 on Test A (mean=70, SD=10) better than 90 on Test B (mean=80, SD=5)?
- Convert to z-scores: Test A: $z = (85-70)/10 = 1.5$, Test B: $z = (90-80)/5 = 2.0$
- Test B score is relatively better!

**2. Finding Probabilities:** They connect to the normal distribution.
- $z = 0$ is at the 50th percentile
- $z = 1.96$ is at the 97.5th percentile
- $z = -1.96$ is at the 2.5th percentile
- This is how we calculate p-values and confidence intervals

**3. Hypothesis Testing:** They're the foundation of statistical tests.
- Large absolute values (far from 0) suggest the null hypothesis is unlikely
- We can look up how extreme a z or t value is using tables or software

### When to Use Z vs T

**Use Z-score when:**
- You know the population standard deviation $\sigma$ (rare)
- Sample size is very large (n > 30) and you're approximating

**Use T-score when:**
- You don't know $\sigma$ and must estimate it from sample (common)
- Sample size is small (n < 30)
- The t-distribution accounts for extra uncertainty from estimating $\sigma$

**Key difference:** The t-distribution has "fatter tails" than the normal distribution, meaning it's more conservative (requires stronger evidence to reject the null hypothesis) when you have small samples.

## Confidence Intervals

A range of values that likely contains the true population parameter with a specified level of confidence.

### How to Interpret

A 95% confidence interval means: If we repeated this study 100 times, about 95 of those intervals would contain the true population parameter.

**Common misconception:** It does NOT mean there's a 95% chance the true value is in this specific interval. The true value either is or isn't in there.

**Example:** "We are 95% confident that the true population mean is between 45 and 55."

### Steps to Construct a Confidence Interval

1. Calculate your sample statistic (like sample mean)
2. Choose your confidence level (typically 90%, 95%, or 99%)
3. Find the critical value (z-score or t-score) for your confidence level
4. Calculate the margin of error = critical value × standard error
5. Confidence interval = sample statistic ± margin of error

**Formula for Confidence Interval (using t-distribution):**

$$\bar{x} \pm t_{\alpha/2} \cdot \frac{s}{\sqrt{n}}$$

**What this means:**
- $\bar{x}$ = sample mean (center of your interval)
- $\pm$ = plus or minus (creates a range)
- $t_{\alpha/2}$ = critical value from t-distribution (depends on confidence level and sample size)
- $\frac{s}{\sqrt{n}}$ = standard error
- The whole thing creates a range: [lower bound, upper bound]

**For large samples (n > 30), using z-distribution:**

$$\bar{x} \pm z_{\alpha/2} \cdot \frac{s}{\sqrt{n}}$$

**What this means:**
- $z_{\alpha/2}$ = critical value from normal distribution
- For 95% confidence, $z_{\alpha/2} = 1.96$
- For 90% confidence, $z_{\alpha/2} = 1.645$
- For 99% confidence, $z_{\alpha/2} = 2.576$

# Hypothesis Testing

A method to test claims about population parameters using sample data.

## The Null and Alternative Hypotheses

**Null Hypothesis (H₀):** The claim of no effect or no difference. What we assume is true until proven otherwise.

**Alternative Hypothesis (H₁ or Hₐ):** The claim we're testing for. What we conclude if we reject H₀.

**Example:**
- $H_0: \mu = 0$ (The new drug has no effect)
- $H_1: \mu \neq 0$ (The new drug has an effect)

## P-Value

The probability of getting results as extreme as yours (or more extreme) if the null hypothesis is true.

**How to use it:**
- Low p-value (≤ 0.05): Strong evidence against $H_0$, reject $H_0$
- High p-value (> 0.05): Weak evidence against $H_0$, fail to reject $H_0$

**Important:** "Fail to reject" is not the same as "accept." We never prove $H_0$ is true.

## Significance Level (α)

The threshold for deciding whether to reject $H_0$. Common choices: 0.05, 0.01, 0.10.

**Rule:** If p-value ≤ $\alpha$, reject $H_0$.

## Steps for Hypothesis Testing

1. State your null and alternative hypotheses
2. Choose a significance level ($\alpha$)
3. Calculate the test statistic from your sample data
4. Find the p-value
5. Make a decision: reject $H_0$ if p-value ≤ $\alpha$
6. Interpret the results in context

## One-Tailed Test

Tests for an effect in one specific direction.

**When to use:** When you only care about increase OR decrease, not both.

**Example (right-tailed):**
- $H_0: \mu \leq 100$
- $H_1: \mu > 100$ (only testing if greater)

**Example (left-tailed):**
- $H_0: \mu \geq 100$
- $H_1: \mu < 100$ (only testing if less)

## Two-Tailed Test

Tests for an effect in either direction.

**When to use:** When you care about any difference, regardless of direction.

**Example:**
- $H_0: \mu = 100$
- $H_1: \mu \neq 100$ (testing if different in either direction)

**Note:** Two-tailed tests are more conservative (harder to reject $H_0$).

## Type I and Type II Errors

**Type I Error (False Positive):** Rejecting $H_0$ when it's actually true. The probability of this is $\alpha$.

**Type II Error (False Negative):** Failing to reject $H_0$ when it's actually false. The probability of this is $\beta$.

**Power:** 

$$\text{Power} = 1 - \beta$$

**What this means:**
- Power is the probability of correctly rejecting a false $H_0$
- Higher power means you're more likely to detect a real effect when it exists
- Typical target: power of 0.80 or higher

**Trade-off:** Decreasing $\alpha$ increases $\beta$. You need to balance the costs of each error type.

# Common Statistical Tests

## T-Test

Used to compare means when you don't know the population standard deviation.

### One-Sample T-Test

**Test Statistic:**

$$t = \frac{\bar{x} - \mu_0}{s / \sqrt{n}}$$

**What this means:**
- $t$ = the t-statistic (how many standard errors away from the hypothesized mean)
- $\bar{x}$ = your sample mean
- $\mu_0$ = the hypothesized population mean (from $H_0$)
- $s$ = sample standard deviation
- $n$ = sample size
- The larger the absolute value of $t$, the stronger the evidence against $H_0$

### Two-Sample T-Test (Independent)

**Test Statistic:**

$$t = \frac{\bar{x}_1 - \bar{x}_2}{\sqrt{\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}}}$$

**What this means:**
- $\bar{x}_1$ and $\bar{x}_2$ = means of the two groups
- $s_1^2$ and $s_2^2$ = variances of the two groups
- $n_1$ and $n_2$ = sample sizes of the two groups
- Numerator: difference between group means
- Denominator: combined standard error of the difference
- Tests whether the difference between means is significant

### Paired T-Test

**Test Statistic:**

$$t = \frac{\bar{d}}{s_d / \sqrt{n}}$$

**What this means:**
- $\bar{d}$ = mean of the differences between paired observations
- $s_d$ = standard deviation of the differences
- $n$ = number of pairs
- Each pair is the same subject measured twice, so we only care about the differences

**Assumptions:** Data is approximately normal, samples are independent (for two-sample).

## Z-Test

Used when you know the population standard deviation (rare in practice).

**Test Statistic:**

$$z = \frac{\bar{x} - \mu_0}{\sigma / \sqrt{n}}$$

**What this means:**
- $z$ = the z-statistic
- $\sigma$ = known population standard deviation (this is what distinguishes z-test from t-test)
- Everything else same as t-test
- Used when sample size is large (n > 30) or population is normal and $\sigma$ is known

## Chi-Square Test

Used for categorical data to test relationships between variables.

**Chi-Square Test Statistic:**

$$\chi^2 = \sum \frac{(O - E)^2}{E}$$

**What this means:**
- $\chi^2$ (chi-square) = the test statistic
- $O$ = observed frequency (what you actually counted)
- $E$ = expected frequency (what you'd expect if $H_0$ was true)
- $(O - E)$ = difference between observed and expected
- Divide by $E$ to standardize (bigger expected counts should allow bigger differences)
- Sum over all categories
- Larger $\chi^2$ means bigger difference between observed and expected

**Chi-square goodness of fit:** Does observed data match expected distribution?

**Chi-square test of independence:** Are two categorical variables related?

## ANOVA (Analysis of Variance)

Used to compare means of three or more groups.

**F-Statistic:**

$$F = \frac{\text{Between-group variability}}{\text{Within-group variability}} = \frac{MS_{\text{between}}}{MS_{\text{within}}}$$

**What this means:**
- $F$ = the F-statistic
- $MS_{\text{between}}$ = mean square between groups (how different the group means are)
- $MS_{\text{within}}$ = mean square within groups (how much variation within each group)
- If groups have different means, numerator will be large
- If groups are similar, $F$ will be close to 1
- Large $F$ suggests group means are significantly different

**Why not multiple t-tests:** Doing multiple tests increases Type I error rate.

**Assumption:** Groups have similar variances (homogeneity of variance).

## Correlation and Regression

**Pearson Correlation Coefficient:**

$$r = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum (x_i - \bar{x})^2 \sum (y_i - \bar{y})^2}}$$

**What this means:**
- $r$ = correlation coefficient (ranges from -1 to +1)
- Numerator: sum of products of deviations (how $x$ and $y$ vary together)
- Denominator: product of standard deviations (standardizes the measure)
- $r = 1$: perfect positive correlation
- $r = -1$: perfect negative correlation
- $r = 0$: no linear correlation

**Simple Linear Regression:**

$$\hat{y} = b_0 + b_1 x$$

**What this means:**
- $\hat{y}$ (y-hat) = predicted value of $y$
- $b_0$ = y-intercept (value of $y$ when $x = 0$)
- $b_1$ = slope (how much $y$ changes for each unit increase in $x$)
- $x$ = predictor variable

**Slope Formula:**

$$b_1 = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sum (x_i - \bar{x})^2}$$

**What this means:**
- Numerator: covariance between $x$ and $y$
- Denominator: variance of $x$
- This gives the best-fitting line through your data points

**Intercept Formula:**

$$b_0 = \bar{y} - b_1 \bar{x}$$

**What this means:**
- Forces the regression line to pass through the point $(\bar{x}, \bar{y})$
- The line goes through the "center" of your data

**Important:** Correlation doesn't imply causation.

# Python Quick Reference

## Pandas - Data Manipulation and Basic Stats

```python
import pandas as pd

# Load data
df = pd.read_csv('data.csv')
df = pd.read_excel('data.xlsx')

# Basic descriptive statistics
df['column'].mean()              # Mean
df['column'].median()            # Median
df['column'].mode()              # Mode
df['column'].std()               # Standard deviation
df['column'].var()               # Variance
df['column'].min()               # Minimum
df['column'].max()               # Maximum
df['column'].quantile(0.25)      # 25th percentile (Q1)
df['column'].quantile(0.75)      # 75th percentile (Q3)

# Summary statistics for all columns
df.describe()                    # Mean, std, min, max, quartiles

# Group by and aggregate
df.groupby('category')['value'].mean()
df.groupby('category')['value'].agg(['mean', 'std', 'count'])

# Count frequencies
df['column'].value_counts()      # Frequency of each value
df['column'].value_counts(normalize=True)  # Proportions

# Correlation
df.corr()                        # Correlation matrix for all numeric columns
df['col1'].corr(df['col2'])      # Correlation between two columns
```

## NumPy - Numerical Operations

```python
import numpy as np

data = [1, 2, 3, 4, 5]

# Basic statistics
np.mean(data)                    # Mean
np.median(data)                  # Median
np.std(data, ddof=1)             # Sample standard deviation
np.var(data, ddof=1)             # Sample variance
np.min(data)                     # Minimum
np.max(data)                     # Maximum
np.percentile(data, 25)          # 25th percentile
np.percentile(data, [25, 50, 75])  # Multiple percentiles

# Random sampling
np.random.seed(42)               # Set seed for reproducibility
np.random.normal(0, 1, 100)      # 100 samples from normal(mean=0, sd=1)
np.random.choice(data, 3)        # Random sample of 3 elements
```

## SciPy Stats - Statistical Tests

```python
from scipy import stats

# T-tests
stats.ttest_1samp(data, popmean=0)           # One-sample t-test
stats.ttest_ind(group1, group2)              # Independent two-sample t-test
stats.ttest_rel(before, after)               # Paired t-test

# Other parametric tests
stats.pearsonr(x, y)                         # Pearson correlation
stats.spearmanr(x, y)                        # Spearman correlation (non-parametric)
stats.f_oneway(group1, group2, group3)       # One-way ANOVA

# Non-parametric tests
stats.mannwhitneyu(group1, group2)           # Mann-Whitney U test
stats.wilcoxon(before, after)                # Wilcoxon signed-rank test
stats.kruskal(group1, group2, group3)        # Kruskal-Wallis test

# Chi-square tests
stats.chi2_contingency(observed_table)       # Chi-square test of independence
stats.chisquare(observed, expected)          # Chi-square goodness of fit

# Normality tests
stats.shapiro(data)                          # Shapiro-Wilk test
stats.normaltest(data)                       # D'Agostino-Pearson test

# Confidence intervals
stats.t.interval(0.95, len(data)-1,          # 95% CI for mean
                 loc=np.mean(data), 
                 scale=stats.sem(data))

# Z-score calculation
stats.zscore(data)                           # Z-scores for all values
```

## Seaborn - Statistical Visualization

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Distribution plots
sns.histplot(data=df, x='column')                    # Histogram
sns.histplot(data=df, x='column', kde=True)          # Histogram with density curve
sns.kdeplot(data=df, x='column')                     # Density plot
sns.boxplot(data=df, x='category', y='value')        # Box plot
sns.violinplot(data=df, x='category', y='value')     # Violin plot

# Relationship plots
sns.scatterplot(data=df, x='var1', y='var2')         # Scatter plot
sns.scatterplot(data=df, x='var1', y='var2', hue='category')  # Colored by category
sns.regplot(data=df, x='var1', y='var2')             # Scatter plot with regression line
sns.lmplot(data=df, x='var1', y='var2', hue='category')  # Regression by category

# Multiple variables
sns.pairplot(df)                                      # Scatter plot matrix
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')  # Correlation heatmap

# Categorical plots
sns.barplot(data=df, x='category', y='value')        # Bar plot with error bars
sns.countplot(data=df, x='category')                 # Count plot
sns.stripplot(data=df, x='category', y='value')      # Strip plot
sns.swarmplot(data=df, x='category', y='value')      # Swarm plot

plt.show()  # Display the plot
```

## Matplotlib - Basic Plotting

```python
import matplotlib.pyplot as plt

# Basic plots
plt.plot(x, y)                   # Line plot
plt.scatter(x, y)                # Scatter plot
plt.bar(categories, values)      # Bar chart
plt.hist(data, bins=20)          # Histogram

# Customization
plt.xlabel('X Label')
plt.ylabel('Y Label')
plt.title('Title')
plt.legend()
plt.grid(True)

plt.show()
```

## Statsmodels - Advanced Statistics

```python
import statsmodels.api as sm
from statsmodels.formula.api import ols

# Linear regression
X = sm.add_constant(X)           # Add intercept
model = sm.OLS(y, X).fit()       # Fit model
print(model.summary())           # Detailed summary

# Linear regression with formula
model = ols('y ~ x1 + x2', data=df).fit()
print(model.summary())

# Logistic regression
model = sm.Logit(y, X).fit()
print(model.summary())

# ANOVA table
from statsmodels.stats.anova import anova_lm
anova_results = anova_lm(model)
```

# Python Examples

Here are complete Python examples using common libraries:

**Calculate descriptive statistics:**
```python
import numpy as np
import pandas as pd

data = [2, 4, 6, 8, 10, 12, 14]

# Using NumPy
print(f"Mean: {np.mean(data)}")
print(f"Median: {np.median(data)}")
print(f"Std Dev: {np.std(data, ddof=1)}")
print(f"Variance: {np.var(data, ddof=1)}")

# Using Pandas
df = pd.DataFrame({'values': data})
print(df.describe())
```

**One-sample t-test:**
```python
from scipy import stats

data = [23, 25, 27, 29, 31, 33, 35]
# Test if mean is significantly different from 25
t_statistic, p_value = stats.ttest_1samp(data, 25)
print(f"T-statistic: {t_statistic:.4f}")
print(f"P-value: {p_value:.4f}")

if p_value < 0.05:
    print("Reject null hypothesis")
else:
    print("Fail to reject null hypothesis")
```

**Two-sample t-test:**
```python
from scipy import stats

group1 = [20, 22, 24, 26, 28]
group2 = [30, 32, 34, 36, 38]
t_stat, p_val = stats.ttest_ind(group1, group2)
print(f"T-statistic: {t_stat:.4f}")
print(f"P-value: {p_val:.4f}")
```

**Confidence interval:**
```python
import scipy.stats as stats
import numpy as np

data = [12, 15, 14, 10, 13, 16, 11]
confidence = 0.95
mean = np.mean(data)
std_err = stats.sem(data)
interval = stats.t.interval(confidence, len(data)-1, mean, std_err)
print(f"95% CI: ({interval[0]:.2f}, {interval[1]:.2f})")
```

**Chi-square test:**
```python
from scipy.stats import chi2_contingency

# Example: relationship between gender and product preference
observed = [[10, 20, 30],   # Male preferences
            [20, 30, 10]]   # Female preferences
chi2, p_val, dof, expected = chi2_contingency(observed)
print(f"Chi-square: {chi2:.4f}")
print(f"P-value: {p_val:.4f}")
print(f"Degrees of freedom: {dof}")
```

**ANOVA:**
```python
from scipy.stats import f_oneway

group1 = [23, 25, 27, 29]
group2 = [30, 32, 34, 36]
group3 = [28, 30, 32, 34]
f_stat, p_val = f_oneway(group1, group2, group3)
print(f"F-statistic: {f_stat:.4f}")
print(f"P-value: {p_val:.4f}")
```

**Correlation and Linear Regression:**
```python
from scipy.stats import pearsonr, linregress
import numpy as np

x = np.array([1, 2, 3, 4, 5])
y = np.array([2, 4, 5, 4, 5])

# Correlation
corr, p_val = pearsonr(x, y)
print(f"Correlation: {corr:.4f}")
print(f"P-value: {p_val:.4f}")

# Linear regression
slope, intercept, r_value, p_value, std_err = linregress(x, y)
print(f"Slope: {slope:.4f}")
print(f"Intercept: {intercept:.4f}")
print(f"R-squared: {r_value**2:.4f}")

# Make predictions
y_pred = slope * x + intercept
print(f"Predictions: {y_pred}")
```

**Visualizations:**
```python
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd

# Create sample data
df = pd.DataFrame({
    'category': ['A', 'A', 'B', 'B', 'C', 'C'],
    'value': [23, 25, 30, 32, 28, 30]
})

# Histogram
sns.histplot(df['value'], kde=True)
plt.title('Distribution of Values')
plt.show()

# Box plot by category
sns.boxplot(data=df, x='category', y='value')
plt.title('Values by Category')
plt.show()

# Scatter plot with regression
sns.regplot(x='x', y='y', data=data_df)
plt.title('Scatter Plot with Regression Line')
plt.show()
```

# Practical Tips

**Always visualize your data first:** Use histograms, box plots, scatter plots to understand distributions and relationships.

**Check assumptions:** Most tests assume normal distribution and/or equal variances. Check these before running tests.

**Sample size matters:** Larger samples give more reliable results and narrower confidence intervals.

**Statistical vs practical significance:** A result can be statistically significant but have a tiny effect size that doesn't matter in real life.

**Report effect sizes:** Don't just report p-values. Include confidence intervals and effect sizes to show magnitude of differences.

**Understand what your test is actually testing:** The p-value tells you the probability of your data given $H_0$, NOT the probability that $H_0$ is true.

**Be careful with multiple comparisons:** Running many tests increases the chance of false positives. Consider corrections like Bonferroni.

**Use the right test:** Make sure your test matches your data type and research question.

**Document your code:** Include comments explaining why you chose specific tests and parameters.
