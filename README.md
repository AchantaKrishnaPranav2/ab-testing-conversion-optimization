# A/B Testing & Conversion Optimization: Landing Page Causal Inference

## Executive Summary
This project evaluates the performance of a new landing page (`treatment`) versus an existing landing page (`control`) across **294,478 user sessions**. By applying statistical hypothesis testing, segmentation analysis, and business impact modeling, this project quantifies the incremental conversion uplift and projects total potential revenue impact.

---

## Key Results & Insights

* **Baseline Conversion Rates:**
  * **Control (`old_page`):** `11.87%`
  * **Treatment (`new_page`):** `17.95%`
* **Relative Uplift:** `+51.2%` increase in conversion rate for the treatment variant.
* **Device & Regional Consistency:** Conversion uplift remained consistent across major device types (Desktop, Mobile, Tablet) and geographic regions.

---

## Project Architecture & Methodology

1. **Data Auditing & Cleaning:**
   * Verified assignment integrity (0 mismatched assignments).
   * Screened for duplicate `user_id` entries to ensure single-session attribution per user.
   * Converted timestamps to datetime objects and verified complete data density (0 missing values).

2. **Exploratory Data Analysis (EDA):**
   * Evaluated behavioral differences (`session_duration`, `pages_visited`) across converting vs. non-converting users.
   * Visualized conversion rates across device types, age cohorts, and top countries.

3. **Statistical Hypothesis Testing:**
   * Two-sample Z-Test for proportions to evaluate statistical significance ($p < 0.05$).
   * Chi-Square Test of Independence across device segments to test for Sample Ratio Mismatch (SRM).

4. **Counterfactual & Business Impact Modeling:**
   * Modeled overall revenue differences assuming full 100% rollout to the `treatment` variant vs. 100% retention on `control`.

---

## Tech Stack
* **Language:** Python
* **Data Manipulation:** `pandas`, `numpy`
* **Visualization:** `matplotlib`, `seaborn`
* **Statistical Analysis:** `scipy.stats`, `statsmodels`

---

## Repository Structure

```text
├── data/
│   └── AB_Testing_Data.csv      # Experimental dataset
├── ab_testing_analysis.py       # Main Jupyter/Colab notebook
├── README.md                    # Project overview and executive summary
