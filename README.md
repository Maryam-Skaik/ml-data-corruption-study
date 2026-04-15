# 🧪 Machine Learning Under Data Corruption

### Missing Values, Outliers, and Preprocessing Strategies

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Completed-success)
![Focus](https://img.shields.io/badge/Focus-Data%20Quality%20Analysis-purple)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📌 Overview

This project explores a simple but important question:

> **Does data cleaning always improve machine learning performance?**

Starting from a real discussion about handling a few missing values in a dataset, this study investigates how different data corruption scenarios affect model performance.

Instead of relying on assumptions, the problem is approached through controlled experiments.

---

## 🎯 Objectives

* Evaluate the impact of **missing data** at different rates
* Compare preprocessing strategies:

  * Dropping rows
  * Median imputation
  * ML-based imputation
* Analyze the effect of **outliers**:

  * Keeping
  * Removing
  * Clipping
* Understand **when preprocessing matters** — and when it does not

---

## 📊 Dataset

* Abalone Dataset
* Regression task
* Target: `rings`

The dataset contains both **numerical and categorical features**, making it suitable for testing preprocessing strategies.

---

## ⚙️ Methodology

### 1. Baseline Setup

* Cleaned invalid values
* Split data into train/test (to avoid leakage)
* Built a consistent preprocessing pipeline

---

### 2. Missing Data Simulation

Missing values were artificially injected into the training data at different rates:

* 5%
* 10%
* 20%
* 40%

### Strategies Compared:

* Drop rows with missing values
* Median imputation
* ML-based imputation (using regression)

---

### 3. Outlier Simulation

Outliers were introduced by modifying feature values (e.g., scaling height).

### Strategies Compared:

* Keep outliers
* Remove outliers
* Clip values within a threshold

---

### 4. Model

* Random Forest Regressor
* Chosen for robustness and minimal preprocessing sensitivity

---

## 📈 Results

### Missing Values

| Missing Rate | Drop  | Median | ML    |
| ------------ | ----- | ------ | ----- |
| 5%           | 2.214 | 2.206  | 2.214 |
| 10%          | 2.205 | 2.222  | 2.225 |
| 20%          | 2.243 | 2.264  | 2.201 |
| 40%          | 2.866 | 2.291  | 2.299 |

---

### Outliers

| Method | RMSE  |
| ------ | ----- |
| Keep   | 2.157 |
| Remove | 2.176 |
| Clip   | 2.156 |

---

## 💡 Key Insights

### Missing Data

* Model performance remains stable under **low to moderate missingness**
* **Dropping rows significantly degrades performance** at high missing rates
* **Median imputation performs comparably to ML-based methods**

---

### Outliers

* Outlier handling had **minimal impact on performance**
* Removing outliers slightly **worsened results**
* Clipping provided **no meaningful improvement**

---

## 🧠 Final Conclusion

> Not all data corruption requires complex preprocessing;
> in many cases, simple strategies are sufficient, while aggressive interventions can degrade performance.

---

## 🚀 Why This Project Matters

This project highlights an important practical insight:

* More preprocessing ≠ better performance
* Simplicity can be effective
* Data quantity and model robustness often matter more

---

## 📂 Project Structure

```
├── ml_data_corruption_study.ipynb
├── README.md
```

---

## 👩‍💻 Author

**Maryam Skaik**

Data Science Enthusiast.
Passionate about experimentation, ML, and practical insights
