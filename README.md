# HealthPlus US Member Segmentation & Retention Analysis
> End-to-end churn analysis of 500,000 health insurance policyholders identifying 
> $732M in at-risk lifetime value and actionable retention strategies by member segment.

## Business Question
Which HealthPlus members are most likely to lapse, what drives their decision to leave, 
and which targeted retention interventions by segment will generate the highest ROI?

## Key Findings
- **24.2% annual lapse rate** — 120,837 members · $732.5M lifetime value at risk per cohort
- **Premium increases** are the #1 controllable driver — churned members faced 8.2% avg 
  increases vs 5.6% for retained (Cohen's d = 0.329)
- **Multi-policy bundling** is the strongest retention lever — 15.2% lapse rate vs 27.0% 
  for single-policy members (11.8pp gap)
- **Autopay enrollment** reduces churn by 8.3pp at near-zero cost — 30.6% of members 
  still not enrolled
- **3 CRM-detectable early warning signals**: competitor quote request (33.9% lapse), 
  complaint filed (33.8%), coverage downgrade (31.1%)

## Tech Stack
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/ScikitLearn-F7931E?logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-FF6600)
![Statsmodels](https://img.shields.io/badge/Statsmodels-Statistics-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)

## Analytical Pipeline
| Stage | Method | Key Output |
|-------|--------|------------|
| Data Cleaning | Imputation, outlier capping, logic checks | 500K clean records · 48 features |
| EDA | Descriptive stats, cross-tabs, correlation | 10+ churn drivers identified |
| Hypothesis Testing | Chi-Square, Welch t-test, ANOVA (7 tests) | All 7 H₀ rejected at α=0.05 |
| Segmentation | RFM scoring + Factor Analysis (PCA) | 5 segments · 62.4% variance explained |
| Churn Model | Logistic Regression, Random Forest, GBM, XGBoost | XGBoost AUC: 0.663 |
| CLV Regression | Multiple Linear Regression | R² = 0.729 |
| Lifecycle Forecast | Exponential Smoothing (additive trend) | 24-month churn projection |

## Member Segments
| Segment | Size | Churn Rate | Avg CLV | Strategy |
|---------|------|-----------|---------|----------|
| Champions | 68,865 | 17.0% | $9,028 | Loyalty program · concierge renewal |
| Loyal Customers | 168,046 | 22.0% | $7,119 | Multi-policy cross-sell · autopay push |
| Potential Loyalists | 193,125 | 26.0% | $5,381 | Bundle offer · 6-month milestone outreach |
| At-Risk | 47,420 | 28.0% | $3,996 | Personal outreach · competitive price match |
| Lost/Price-Sensitive | 22,544 | 30.0% | $3,097 | Subsidy check · hardship program |

## Top Churn Model Features
| Rank | Feature | Importance |
|------|---------|-----------|
| 1 | multi_policy_flag | 0.172 |
| 2 | premium_change_pct | 0.165 |
| 3 | autopay_enabled | 0.061 |
| 4 | num_policies | 0.050 |
| 5 | quote_requested_flag | 0.040 |

## Recommendations
1. Flag members facing premium increases above 8% for a personal retention call before renewal
2. Target 193,125 Potential Loyalists with a multi-policy bundling offer
3. Enroll all new members in autopay at sign-up — 8.3pp churn reduction at no additional cost

## Files
| File | Description |
|------|-------------|
| `HEALTHPLUS US MEMBER SEGMENTATION & RETENTION ANALYSIS.ipynb` | Full analysis notebook |
| `HEALTHPLUS US MEMBER SEGMENTATION & RETENTION ANALYSIS_Final Report.pdf` | Executive summary and comprehensive analysis report |
