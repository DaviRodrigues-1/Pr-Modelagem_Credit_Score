# 📊 Customer Data Analysis – Missing Value Strategy & Exploratory Insights

## 📌 Overview

This project presents an exploratory data analysis (EDA) and preprocessing workflow applied to a customer dataset containing 164 observations.

A key challenge addressed in this project was handling missing values in the **Age** variable (~20% missing data) while preserving statistical integrity and avoiding distribution distortion.

The notebook demonstrates structured reasoning in data cleaning, visualization, and preparation for machine learning.

---

## 🎯 Objectives

- Perform exploratory data analysis (EDA)
- Identify and analyze missing values
- Apply statistically coherent imputation strategies
- Preserve distribution consistency
- Prepare the dataset for modeling

---

## 📂 Dataset Summary

- **Total rows:** 164  
- **Missing values in Age:** 34 (~20%)  
- **Key variables:**
  - Age
  - Marital Status
  - (Other relevant features)

---

## ⚠️ Main Challenge: Missing Values in Age

A simple median imputation created artificial peaks in the distribution, distorting visual analysis.

To solve this, a **group-based mean imputation by Marital Status** was applied:

```python
df['Age'] = df.groupby('Marital Status')['Age'] \
              .transform(lambda x: x.fillna(x.mean()))
```

### ✅ Why This Approach?

- Preserves the relationship between Age and Marital Status
- Avoids artificial clustering
- Reduces statistical bias
- Produces more reliable visualizations and modeling inputs

---

## 📊 Exploratory Analysis

The project includes:

- Distribution analysis
- Age vs Marital Status visualization
- Missing value diagnostics
- Post-imputation validation

---

## 🛠️ Technologies Used

- Python 3
- Pandas
- NumPy
- Matplotlib
- Plotly
- Scikit-learn

---

## 🚀 How to Run

Clone the repository:

```bash
git clone https://github.com/your-username/your-repository-name.git
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the notebook:

```bash
jupyter notebook
```

---

## 📈 Key Takeaways

- Missing data handling requires statistical reasoning, not only technical fixes.
- Group-based imputation can preserve structural patterns better than global metrics.
- Data preprocessing decisions directly impact model reliability.

---

## 📌 Future Improvements

- Predictive imputation (regression-based)
- Feature engineering
- Model training & validation
- Larger dataset expansion

---

## 👤 Author

Davi Rodrigues Trindade
Data Science Student  
LinkedIn: https://www.linkedin.com/in/davirodriguestrindade/
