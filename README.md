📊 Customer Data Analysis – Missing Value Strategy & Exploratory Insights
📌 Overview

This project presents an exploratory data analysis (EDA) and preprocessing workflow applied to a customer dataset with 164 observations.

A key challenge addressed in this project was handling missing values in the Age variable (approximately 20% missing), ensuring statistical consistency without distorting the data distribution.

The notebook demonstrates structured decision-making in data cleaning, visualization, and preparation for modeling.

🎯 Objectives

Perform exploratory data analysis (EDA)

Identify and analyze missing values

Apply statistically coherent imputation strategies

Preserve distribution integrity

Prepare the dataset for machine learning modeling

📂 Dataset Summary

Total rows: 164

Target variable: (if applicable, insert here)

Key variables:

Age

Marital Status

(add other relevant features)

⚠️ Key Challenge: Missing Values in Age

34 missing values (~20% of dataset)

Simple median imputation created artificial distribution spikes

Required a more structured solution

🧠 Solution Strategy

Instead of global median imputation, Age was imputed using group-based mean imputation by Marital Status, preserving demographic structure:

df['Age'] = df.groupby('Marital Status')['Age'] \
              .transform(lambda x: x.fillna(x.mean()))
Why this approach?

Maintains relational consistency between Age and Marital Status

Avoids artificial distribution peaks

Reduces statistical bias

Produces more reliable visualizations and modeling inputs

📊 Exploratory Analysis

The notebook includes:

Distribution analysis

Relationship between Age and Marital Status

Visual correlation insights

Data balance evaluation after imputation

🛠️ Technologies Used

Python 3

Pandas

NumPy

Matplotlib

Plotly

Scikit-learn
