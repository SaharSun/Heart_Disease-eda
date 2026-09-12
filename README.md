# ❤️ Heart Disease — Exploratory Data Analysis

A complete, portfolio-grade exploratory data analysis (EDA) of the UCI Heart Disease dataset — data quality auditing, univariate/bivariate/multivariate analysis, statistical significance testing (Welch's t-test, Chi-square, Cramér's V), and subgroup analysis by age and gender.

> **Scope note:** this is an educational/analytical project, not a clinical or diagnostic tool. Statistical associations shown here do not imply causation.

---

## 📊 Key Findings

- The dataset is clean (no missing values) after removing **1 duplicate record** (303 → 302 patients).
- The target class is well balanced (~54% diseased vs. ~46% healthy) — no resampling needed for modeling.
- **`thalach`** (max heart rate), **`cp`** (chest pain type), **`exang`**, **`oldpeak`**, and **`ca`** show the strongest, statistically significant relationships with heart disease.
- Women in this dataset show a notably higher disease rate than men (75.0% vs. 44.7%), consistent across most other risk factors — though the smaller female sample size (n=96) calls for caution.
- No severe multicollinearity was found between independent features.

## 📓 Notebook Structure

| # | Section | What it covers |
|---|---------|-----------------|
| 1 | Import Libraries and Visual Settings | Consistent color system + plotting theme used throughout |
| 2 | Data Loading & Overview | Shape, dtypes, first look |
| 3 | Data Quality & Cleaning | Missing values, duplicates, implausible zero values |
| 4 | Data Dictionary & Feature Types | Human-readable labels for every coded column |
| 5 | Descriptive Statistics | Summary stats, skewness/kurtosis, distribution plots |
| 6 | Outlier Detection | IQR-based screening (flagged, not deleted) |
| 7 | Target Analysis | Class balance |
| 8 | Bivariate Analysis | Feature vs. target relationships (scatter, violin, stacked bar, age groups) |
| 9 | Demographic Subgroup Analysis | Disease rate by gender, across other risk factors |
| 10 | Correlation & Association Analysis | Pearson correlation + ranked bar chart |
| 11 | Statistical Significance & Effect Size | Welch's t-test, Chi-square, Cramér's V, combined feature ranking |
| 12 | Multivariate Analysis | Pairplot of key features |
| 13 | Key Findings & Modeling Recommendations | Auto-generated summary + next steps |

## 🗂️ Dataset

- **Records:** 303 (302 after deduplication)
- **Features:** 13 clinical attributes + binary target (`0` = no disease, `1` = disease)

## 🛠️ Tech Stack

- Python 3.11+
- pandas, numpy
- matplotlib, seaborn
- scipy (statistical tests)

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/heart-disease-eda.git
cd heart-disease-eda

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch Jupyter and open the notebook
jupyter notebook heart_eda_portfolio.ipynb
```

Place `heart.csv` in the same directory as the notebook before running (or update the path in the second cell).

## 📁 Repository Structure

```
heart-disease-eda/
├── Heart_Disease.ipynb    # main analysis notebook
├── heart.csv                   # dataset
├── requirements.txt            # dependencies
├── README.md
└── LICENSE
```

## 📌 Notes on Methodology

- Categorical associations use **Cramér's V** rather than Pearson correlation, since numeric codes for categorical features (e.g. `thal`, `cp`) don't have a real linear ordering.
- Multiple hypothesis tests are run without correction — p-values here should be read as exploratory evidence, not confirmatory proof.
- Outliers are flagged via the 1.5×IQR rule but intentionally **not removed**, since unusual clinical readings often reflect real patient variation.


## 👤 Author

**Saahar Khorshid**
[LinkedIn](https://www.kaggle.com/saharkhorshid)  · [Kaggle](https://www.linkedin.com/in/saharkhorshid/)
