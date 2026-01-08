# Exploratory Data Analysis (EDA) — Practice Notebook

A friendly, practical EDA guide implemented as a Jupyter Notebook (practice.ipynb). This notebook walks through comprehensive exploratory data analysis using Python (Pandas, Seaborn, Matplotlib, Plotly) on Seaborn's built-in Titanic dataset. It is aimed at beginners and intermediate users and includes a light "desi" tone for engagement.

---

## Contents / Overview

The notebook is organized into four main pillars:

1. Data composition
   - Counts, unique categories, class imbalance, categorical summaries.
2. Data distribution
   - Histograms, KDE, boxplots, log transforms, skew detection.
3. Data relationships
   - Correlation matrix, pairplots, violin/box plots, interactive Plotly visualizations.
4. Data comparison
   - Groupby/pivot tables, survival rates, chi-square and t-tests.

Additional sections:
- Data cleaning techniques (missing values, imputation, type conversions)
- Outlier detection (IQR method)
- Best practices & tips
- Optional saving of cleaned dataset (CSV / Parquet)

The notebook keeps a copy of the original data as `df_original` so you can always revert.

---

## Files

- practice.ipynb — main EDA notebook (this file)
- (optional) titanic_clean.csv or titanic_clean.parquet — generated if you enable the save cells in the notebook

---

## Dependencies

The notebook uses the following packages (tested with Python 3.12 kernel in the notebook metadata):

- pandas
- numpy
- matplotlib
- seaborn
- plotly
- missingno
- scipy

Install with pip if needed:

```bash
pip install pandas numpy matplotlib seaborn plotly missingno scipy
```

---

## How to run

1. Clone or download the repository / notebook file to your machine.
2. (Optional) Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate   # macOS / Linux
   .venv\Scripts\activate      # Windows
   ```
3. Install dependencies (see Dependencies section).
4. Start Jupyter Notebook or Jupyter Lab:
   ```bash
   jupyter notebook
   # or
   jupyter lab
   ```
5. Open `practice.ipynb` and run cells from top to bottom. The notebook relies on Seaborn's built-in `titanic` dataset (no external file download required).

Notes:
- For interactive Plotly charts, use a browser environment where Plotly outputs are supported.
- If running in Google Colab, comment/uncomment pip installs as needed and upload the notebook or open from Google Drive/GitHub.

---

## Quick walkthrough / What you will see

- Library import and environment setup (plots, pandas display options)
- Loading data: `df = sns.load_dataset('titanic')`, and `df_original = df.copy()`
- Missingness inspection with `missingno` (matrix & bar)
- Practical imputations:
  - `age` imputed with median grouped by `pclass` and `sex`
  - `embarked` filled using mode
  - `deck` flagged as `'Missing'`
- Conversion of several columns to categorical type for better plotting/memory
- Visual exploration:
  - Count plots for category composition
  - Histograms, KDE and log transform for skewed numeric features (`fare`)
  - Boxplots, violin plots and pairplots
  - Interactive Plotly scatter and animated histogram examples
- Group comparisons and statistical tests:
  - Survival rates by class/sex with pivot tables and heatmaps
  - Chi-square and t-test examples

---

## Recommendations & Best Practices

- Always inspect shape, `df.info()` and `df.describe()` first.
- Visualize missingness early (use `missingno`).
- Keep a copy of the original dataset so you can revert (`df_original`).
- Document decisions you make during cleaning (why you imputed or dropped rows).
- Use log transforms for heavily right-skewed numeric variables before modeling/plotting.
- Use pivot tables and grouped visualizations for comparing segments.

---

## Next ideas / Extensions

- Add modeling-ready feature engineering (one-hot / target encoding, interactions).
- Build a classification baseline (e.g., logistic regression, random forest) to predict `survived`.
- Add cross-validation and SHAP-based explanations for model interpretability.
- Expand dataset sources (merge with external passenger features if available).

---

## License & Credits

- This notebook is provided "as-is". You can reuse and adapt it for personal and educational projects.
- Inspired by common EDA workflows and Seaborn's Titanic example.
- Created by: jenax-zerox

---

## Contact

If you want me to expand this notebook (feature engineering, modeling, or automated reporting), ping: jenax-zerox

Enjoy the EDA — and chai pe bulao agar kabhi Lahore ya Karachi aa jao. ☕🇵🇰
