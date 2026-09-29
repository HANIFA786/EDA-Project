# Exploratory Data Analysis (EDA) – Adult Dataset

## 📌 Project Overview

This project focuses on performing **Exploratory Data Analysis (EDA)** on the Adult dataset using Python. The analysis explores demographic, education, occupation, working hours, income, and other attributes.

The project uses **Pandas, NumPy, Matplotlib, Seaborn, and SciPy** to clean, analyze, summarize, and visualize the data.

---

## 🎯 Objectives

The main objectives of this project are:

* Understand the structure of the dataset
* Perform data cleaning and preprocessing
* Identify and handle missing values
* Perform statistical analysis
* Analyze different income categories
* Analyze education, occupation, age, and working hours
* Detect outliers
* Perform basic data visualization
* Generate meaningful insights from the dataset

---

## 📂 Dataset

**Dataset:** Adult Dataset

The dataset contains information related to individuals, including:

* Age
* Workclass
* Education
* Education Number
* Marital Status
* Occupation
* Relationship
* Gender
* Capital Gain
* Capital Loss
* Hours per Week
* Native Country
* Income

The dataset is loaded from:

```python
pd.read_csv("adult.csv")
```

---

## 🛠️ Technologies & Libraries Used

| Technology       | Purpose                        |
| ---------------- | ------------------------------ |
| Python           | Programming language           |
| Pandas           | Data manipulation and analysis |
| NumPy            | Numerical calculations         |
| Matplotlib       | Data visualization             |
| Seaborn          | Statistical visualization      |
| SciPy            | Z-score and outlier analysis   |
| Jupyter Notebook | Development environment        |

---

## 🔍 Exploratory Data Analysis

### 1. Dataset Inspection

The project includes basic dataset inspection using:

```python
df.head()
df.tail()
df.shape
df.dtypes
df.columns
df.count()
df.info()
df.describe()
```

These operations help understand the dataset's structure, columns, data types, and statistical characteristics.

---

### 2. GroupBy Analysis

The project analyzes different income categories using `groupby()`.

For example:

```python
df.groupby("Income").agg({
    "Age": "mean",
    "Hours per Week": "mean"
})
```

This helps compare average age and working hours between income categories.

---

### 3. Value Counts

The project uses `value_counts()` to analyze categorical variables.

Examples include:

```python
df["Education"].value_counts()
df["Income"].value_counts()
df["Native Country"].value_counts()
```

This helps identify the frequency of different categories.

---

### 4. Statistical Analysis

Statistical calculations are performed on columns such as:

* Age
* Hours per Week
* Capital Gain
* Capital Loss

The project calculates:

* Mean
* Median
* Minimum
* Maximum
* Standard deviation

Example:

```python
df["Hours per Week"].agg([
    "mean",
    "median",
    "max",
    "min"
])
```

---

## 🧹 Data Cleaning

The project includes several data-cleaning techniques.

### Handling Missing Values

Missing values are identified using:

```python
df.isna().sum()
```

The project also replaces `"?"` values with missing values:

```python
data = data.replace(" ?", None)
```

### Filling Missing Values

Different techniques are explored, including:

**Mean:**

```python
df["Age"] = df["Age"].fillna(df["Age"].mean())
```

**Median:**

```python
df["Hours per Week"] = df["Hours per Week"].fillna(
    df["Hours per Week"].median()
)
```

**Mode:**

```python
df["Workclass"] = df["Workclass"].fillna(
    df["Workclass"].mode()[0]
)
```

Constant values are also used for categorical columns such as Workclass and Occupation.

---

## 🗑️ Removing Missing Data

The project demonstrates removing rows containing missing values:

```python
df.dropna()
```

It also demonstrates removing rows based on a specific column:

```python
df.dropna(subset=["Occupation"])
```

The `Native Country` column is also removed during the cleaning exercises.

---

## 📊 Outlier Detection

The project explores different methods for detecting and handling outliers.

### IQR Method

The Interquartile Range is calculated using:

```python
Q1 = df["Hours per Week"].quantile(0.25)
Q3 = df["Hours per Week"].quantile(0.75)

IQR = Q3 - Q1
```

Lower and upper bounds are calculated to identify potential outliers.

### Z-Score

Z-score analysis is performed using SciPy:

```python
from scipy.stats import zscore

df["Age_zscore"] = zscore(df["Age"])
```

Values with an absolute Z-score greater than 3 are considered potential outliers in this analysis.

### Winsorization

Winsorization is also explored:

```python
from scipy.stats.mstats import winsorize

df["Age_winsorized"] = winsorize(
    df["Age"],
    limits=[0, 0.5]
)
```

---

## 📈 Data Visualization

The project includes basic visualizations using Matplotlib and Seaborn.

### Age Distribution

A histogram is created to understand the distribution of age:

```python
data["Age"].hist(
    bins=20,
    edgecolor="black"
)
```

### Gender Distribution

A pie chart is used to visualize gender distribution:

```python
gender_counts = data["Gender"].str.strip().value_counts()

plt.pie(
    gender_counts,
    labels=gender_counts.index,
    autopct="%1.1f%%"
)
```

### Age vs Education Number

A scatter plot is created to examine the relationship between age and education number:

```python
plt.scatter(
    data=df,
    x="Age",
    y="EducationNum"
)
```

---

## 📋 Key Analysis Performed

The notebook covers the following analysis tasks:

* Average age by income category
* Average working hours by income category
* Dataset rows and columns
* First and last records
* Unique Workclass values
* Education frequency
* Income frequency
* Native Country frequency
* Missing-value analysis
* Average, median, minimum, and maximum working hours
* Capital Gain and Capital Loss statistics
* Education-wise age analysis
* Income-wise summary
* Age filtering
* Income filtering
* Education filtering
* Correlation analysis
* Mode analysis
* Missing-value treatment
* IQR-based outlier analysis
* Z-score outlier analysis
* Winsorization
* Age distribution
* Gender distribution
* Age vs Education Number visualization

---

## 💡 Skills Demonstrated

Through this project, I practiced:

* Python Programming
* Pandas
* NumPy
* Data Cleaning
* Data Preprocessing
* Exploratory Data Analysis
* Statistical Analysis
* GroupBy and Aggregation
* Filtering and Sorting
* Missing Value Handling
* Outlier Detection
* Data Visualization
* Matplotlib
* Seaborn
* SciPy

---

## 📁 Project Structure

```text
EDA-Project/
│
├── EDA_Project.ipynb
├── adult.csv
└── README.md
```

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/your-username/your-repository-name.git
```

### 2. Open the project

Open `EDA_Project.ipynb` using:

* Jupyter Notebook
* JupyterLab
* Google Colab
* VS Code

### 3. Install required libraries

```bash
pip install pandas numpy matplotlib seaborn scipy
```

### 4. Run the notebook

Run the cells in `EDA_Project.ipynb` sequentially.

---

## 👩‍💻 Author

**Hanifa Begum**

MCA – Andhra University

### Skills

Python | SQL | Pandas | NumPy | Power BI | Data Analysis | Data Visualization

---

## ⭐ Project

If you find this project useful, feel free to ⭐ the repository.
