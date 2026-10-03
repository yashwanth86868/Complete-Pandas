# 🐼 Pandas Data Analysis — From Basics to Visualization

> A hands-on Pandas notebook for learning how to load, inspect, slice, filter, analyze, and visualize real-world tabular data.

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C9BD1)](https://seaborn.pydata.org/)

---

## 📌 About This Repository

This repository contains my **Pandas practice notebook**, created to build a strong foundation in data analysis with Python.

Instead of only learning syntax, the notebook works with a real tabular dataset containing **195 rows and 5 columns**:

| Column | Type | Description |
|---|---|---|
| `CountryName` | Categorical | Country name |
| `CountryCode` | Categorical | Country code |
| `BirthRate` | Numerical | Birth-rate value |
| `InternetUsers` | Numerical | Internet-user percentage/value |
| `IncomeGroup` | Categorical | Income classification |

The notebook gradually moves from basic DataFrame operations to filtering, feature creation, and visual exploration.

---

## 🎯 What You'll Learn

### 1. Load Data with Pandas

```python
import pandas as pd

df = pd.read_excel("data.xlsx")
```

Learn how to bring Excel data into a Pandas DataFrame.

---

### 2. Understand Your DataFrame

The notebook practices:

```python
df.shape
df.columns
df.dtypes
df.info()
df.head()
df.tail()
```

These operations help answer questions such as:

- How many rows and columns are present?
- What are the column names?
- What data types are being used?
- What does the dataset look like?
- Are there missing values?

---

### 3. Check Missing Values

```python
df.isnull()
df.isna()
df.isnull().sum()
```

You will see how `isnull()` and `isna()` can be used to inspect missing values.

---

### 4. Select and Slice Data

The notebook includes practical slicing examples:

```python
df[:]
df[::-1]
df[0:200:30]
df[50:101]
df[::3]
df[::-3]
```

You can use these examples to understand how Pandas handles rows, ranges, and step-based slicing.

---

### 5. Select Columns

Single-column selection:

```python
df["CountryName"]
```

Multiple-column selection:

```python
df[["CountryName", "CountryCode"]]
```

---

### 6. Separate Numerical and Categorical Data

A useful step before Machine Learning is understanding the different types of features.

Numerical columns:

```python
df_num = df[["BirthRate", "InternetUsers"]]
```

Categorical columns:

```python
df_cat = df[["CountryName", "CountryCode", "IncomeGroup"]]
```

This notebook also compares their shapes and descriptive statistics.

---

### 7. Descriptive Statistics

Explore your dataset using:

```python
df.describe()
df.describe(include="all")
df.describe(include=["object"])
```

For numerical data:

```python
df_num.describe()
```

The notebook also demonstrates:

```python
df_num.describe().transpose()
```

to transpose the statistical summary.

---

### 8. Rename DataFrame Columns

The notebook demonstrates how column names can be changed:

```python
df.columns = ["a", "b", "c", "d", "e"]
```

and then restored to meaningful names.

---

### 9. Create a New Calculated Column

One of the most useful Pandas operations is creating features from existing columns.

Example:

```python
df["myCalc"] = df.BirthRate * df.InternetUsers
```

This demonstrates how Pandas can perform calculations across entire columns.

---

### 10. Remove a Column

The notebook also demonstrates removing a column:

```python
df = df.drop("myCalc", axis=1)
```

This is useful when a temporary or unwanted feature is no longer required.

---

### 11. Filter Data

Find countries where Internet Users are below 2:

```python
df[df["InternetUsers"] < 2]
```

Find countries where Birth Rate is greater than 40:

```python
df[df["BirthRate"] > 40]
```

Combine multiple conditions:

```python
df[
    (df.BirthRate > 40) &
    (df.InternetUsers < 2)
]
```

This is an important concept for real-world data analysis.

---

### 12. Explore Categorical Data

The notebook uses:

```python
df["IncomeGroup"].unique()
```

to find unique categories and:

```python
df["IncomeGroup"].nunique()
```

to count the number of unique categories.

---

## 📊 Data Visualization

The notebook also introduces visualization using **Matplotlib and Seaborn**.

### Distribution Plot

```python
sns.displot(df["InternetUsers"])
```

With bins:

```python
sns.displot(df["InternetUsers"], bins=15)
```

### Box Plot

```python
sns.boxplot(
    data=df,
    x="IncomeGroup",
    y="BirthRate"
)
```

This helps compare the distribution of Birth Rate across income groups.

### Regression Plot

```python
sns.lmplot(
    data=df,
    x="InternetUsers",
    y="BirthRate"
)
```

The notebook also explores the relationship between Internet Users and Birth Rate by Income Group using `hue`.

---

## 🧰 Libraries Used

```text
Python
│
├── Pandas       → Data loading & manipulation
├── Matplotlib   → Visualization
├── Seaborn      → Statistical visualization
└── Jupyter      → Interactive learning environment
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Pandas.git
cd Pandas
```

### 2. Install dependencies

```bash
pip install pandas matplotlib seaborn openpyxl jupyter
```

### 3. Start Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open

```text
Pandas.ipynb
```

> **Note:** The notebook originally loads an Excel file with `pd.read_excel()`. If you run it on your own computer, update the file path to point to your local `data.xlsx` file.

---

## 🗂️ Suggested Repository Structure

```text
Pandas/
│
├── Pandas.ipynb
├── data.xlsx
├── README.md
└── requirements.txt
```

---

## 💡 Why This Notebook Is Useful

This notebook is especially useful for beginners who want to understand **what Pandas actually does with data**.

It follows a practical learning flow:

```text
Load Data
    ↓
Inspect Data
    ↓
Understand Columns & Data Types
    ↓
Slice & Select
    ↓
Check Missing Values
    ↓
Separate Numerical & Categorical Data
    ↓
Descriptive Statistics
    ↓
Create Features
    ↓
Filter Data
    ↓
Visualize Data
```

These skills form an important foundation for:

- 📊 Data Analysis
- 🔎 Exploratory Data Analysis (EDA)
- 🤖 Machine Learning
- 🧠 Artificial Intelligence
- 📈 Data Science

---

## 👨‍💻 Author

**Yashwanth Balija**

Python | Machine Learning | NLP | Generative AI

---

## ⭐ If This Helps You

If you're learning Pandas, feel free to **fork this repository**, experiment with the notebook, and add your own datasets and analysis.

⭐ **Star the repository if you find it useful!**

---

### 📚 Learning Roadmap

```text
Python
  ↓
NumPy
  ↓
Pandas  ← You are here
  ↓
Matplotlib / Seaborn
  ↓
EDA
  ↓
Machine Learning
  ↓
NLP
  ↓
Generative AI
```
