# Manufacturing Process Analysis: Machine Operating Conditions & Supplier Quality

## Overview

This project explores manufacturing machine operating data across three production machines to identify patterns in operating conditions, batch variability, and quality outcomes. Using exploratory data analysis and unsupervised clustering, the analysis surfaces actionable insights about machine performance consistency and supplier relationships — the kind of questions that matter on a real production floor.

**Domain context:** Drawing on a background in regulated manufacturing and quality systems, this analysis approaches the data not just as a modeling exercise but as a real operations problem: where are the machines behaving differently, and what does that tell us about process control?

---

## Business Questions

- Do machine operating conditions (x1–x4) vary significantly across the three machines?
- How does batch variability compare within and across machines?
- Do supplier characteristics correlate with operating condition patterns?
- Can unsupervised clustering identify meaningful groupings that align with known production categories?

---

## Dataset

| File | Description |
|---|---|
| `midterm_machine_01.csv` | Operating data for Machine 1 (5,152 records) |
| `midterm_machine_02.csv` | Operating data for Machine 2 |
| `midterm_machine_03.csv` | Operating data for Machine 3 |
| `midterm_supplier.csv` | Supplier metadata |
| `midterm_results.csv` | Quality outcome results |

**Key variables:**
- `x1` through `x4` — continuous operating condition measurements
- `Batch` — production batch identifier
- `s_id` — supplier identifier
- `machine_id` — machine identifier (derived)

---

## Methods

### Exploratory Data Analysis
- Essential data profiling: shape, dtypes, missing values, unique value counts
- Marginal distribution visualizations (histograms) for all continuous variables
- Cross-machine comparisons of operating variable distributions
- Batch-level variability analysis
- Pairwise relationship plots grouped by machine and batch

### Data Integration
- Concatenated three machine datasets into a unified DataFrame with machine_id tracking
- Merged supplier and results data to enable cross-dataset analysis

### Cluster Analysis (KMeans)
- Clustered on continuous operating inputs (x1–x4)
- Evaluated 2-cluster solution for baseline grouping
- Used elbow method (within-cluster sum of squares) to identify optimal cluster count
- Interpreted cluster profiles against known categorical groupings (machine, batch, quality outcomes)

---

## Key Findings

- Operating variables x1–x4 show measurable differences across the three machines, suggesting machine-specific calibration or wear patterns
- Batch variability is not uniform — certain batches exhibit wider operating ranges, which may indicate process instability
- KMeans clustering reveals groupings that partially align with machine identity, suggesting machine operating signature is a dominant source of variation in the data
- Supplier characteristics show correlational patterns with certain operating condition clusters

---

## Tools & Libraries

| Library | Purpose |
|---|---|
| `pandas` | Data loading, merging, grouping |
| `numpy` | Numerical operations |
| `matplotlib` | Base visualizations |
| `seaborn` | Statistical visualizations |
| `scikit-learn` | KMeans clustering, StandardScaler, PCA |
| `scipy` | Hierarchical clustering reference |

---

## How to Run

```bash
# Clone the repository
git clone https://github.com/regis-stong/manufacturing-process-analysis.git
cd manufacturing-process-analysis

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn scipy

# Launch the notebook
jupyter notebook manufacturing_eda_clustering.ipynb
```

> **Note:** The five source CSV files must be placed in the same directory as the notebook before running.

---

## About

**Regis Stong** | MS Data Science Candidate, University of Pittsburgh (Graduating Fall 2026)

10 years of experience in quality systems, laboratory analytics, and regulated manufacturing environments across pharma, food safety, and industrial operations. This project reflects my interest in applying data science methods to the kinds of operational problems I've worked with directly.

[LinkedIn](https://www.linkedin.com/in/regis-stong-0573a8266) | [GitHub](https://github.com/regis-stong)
