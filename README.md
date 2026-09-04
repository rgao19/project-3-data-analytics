# Minimum Wage and Employment: A Difference-in-Differences Analysis

## Overview

This project examines the employment effect of New Jersey's 1992 minimum-wage increase using a quasi-experimental Difference-in-Differences (DiD) research design.

In April 1992, New Jersey increased its minimum wage from **$4.25 to $5.05 per hour**, while neighboring Pennsylvania maintained its minimum wage at $4.25. This policy difference provides a natural setting for comparing changes in fast-food employment across the two states.

The analysis is based on the classic minimum-wage study by **David Card and Alan B. Krueger** and focuses on employment at fast-food restaurants surveyed before and after the policy change.

---

## Research Question

**Did New Jersey's 1992 minimum-wage increase reduce employment in the fast-food industry relative to Pennsylvania?**

The analysis treats:

- **New Jersey** as the treatment group
- **Eastern Pennsylvania** as the comparison group
- **February 1992** as the pre-treatment period
- **November 1992** as the post-treatment period

The primary outcome is **full-time-equivalent (FTE) employment per restaurant**.

---

## Empirical Strategy

The baseline Difference-in-Differences model is:

```text
Employment_it = β₀ + β₁ NJ_i + β₂ Post_t + β₃ (NJ_i × Post_t) + ε_it
```

where **β₃** represents the estimated treatment effect of the minimum-wage increase.

Because restaurants are observed across survey periods, the baseline regression uses **standard errors clustered at the restaurant level**.
---

## Main Result

The baseline Difference-in-Differences estimate is:

**+2.754 FTE employees per restaurant**

with:

- Clustered standard error: **1.307**
- p-value: **0.035**
- 95% confidence interval: **[0.193, 5.315]**

Average employment declined in Pennsylvania during the study period while increasing slightly in New Jersey, producing a positive relative employment change.

The baseline estimate therefore provides **no evidence that New Jersey's minimum-wage increase reduced fast-food employment relative to Pennsylvania** in this sample.

---

## Robustness Analysis

Several alternative specifications are used to examine whether the main result is sensitive to sample construction or model specification.

| Specification | DiD Estimate | Standard Error | p-value |
|---|---:|---:|---:|
| Baseline DiD | 2.754 | 1.307 | 0.035 |
| Balanced Panel | 2.750 | 1.339 | 0.040 |
| Adjusted DiD | 2.813 | 1.316 | 0.033 |
| Restaurant Fixed Effects (Balanced) | 2.750 | 1.893 | 0.146 |

The point estimates remain close to **2.75–2.81 FTE employees** across specifications.

The fixed-effects specification produces a nearly identical point estimate but a substantially wider confidence interval, indicating that statistical precision is sensitive to specification even though the estimated effect itself is highly stable.

---

## Exploratory Heterogeneity

The project also examines whether estimated treatment effects differ across major restaurant chains.

Estimated effects vary across **Burger King, KFC, Roy Rogers, and Wendy's**. However, the 95% confidence interval for every chain-specific estimate includes zero.

These results are therefore interpreted as **exploratory evidence of possible heterogeneity**, rather than evidence of systematic differences in treatment effects across chains.

---

## Identification and Limitations

A causal interpretation of the Difference-in-Differences estimate relies on the **parallel-trends assumption**: without the minimum-wage increase, employment in New Jersey and Pennsylvania would have followed similar trends.

An important limitation is that the dataset contains only **one pre-treatment and one post-treatment survey wave**. Consequently, pre-treatment employment trends cannot be directly examined or formally tested using multiple pre-policy periods.

Other limitations include:

- Missing employment observations reduce the usable estimation sample.
- The study focuses specifically on fast-food restaurants in New Jersey and eastern Pennsylvania.
- Chain-specific estimates rely on relatively small comparison samples and are imprecise.
- Other contemporaneous economic changes could affect the estimates if they influenced New Jersey and Pennsylvania differently.
- Statistical significance varies across specifications despite stable point estimates.

The results should therefore be interpreted within this specific quasi-experimental setting rather than as a universal estimate of the employment effect of minimum-wage policy.

---

## Conclusion

Across the baseline, balanced-panel, covariate-adjusted, and fixed-effects specifications, the estimated relative employment effect remains approximately **+2.75 to +2.81 FTE employees per restaurant**.

Taken together, the results **do not support the prediction that New Jersey's 1992 minimum-wage increase caused a relative decline in fast-food employment during the study period**.

At the same time, variation in statistical precision across specifications and the limitations of the two-period research design warrant caution in interpreting the positive point estimates as a general causal effect.

More broadly, this project demonstrates how **quasi-experimental methods and causal inference** can be used to move beyond simple correlations when evaluating public-policy interventions.

---

## Methods and Tools

**Methods**

- Difference-in-Differences
- OLS Regression
- Cluster-Robust Inference
- Restaurant Fixed Effects
- Balanced-Panel Analysis
- Covariate Adjustment
- Heterogeneous Treatment Effect Analysis

**Tools**

- Python
- Pandas
- NumPy
- Statsmodels
- Matplotlib
- Seaborn
- Google Colab

---

## Repository Structure

```text
project-3-data-analytics/
├── README.md
├── minimum_wage_did_analysis.ipynb
└── requirements.txt
