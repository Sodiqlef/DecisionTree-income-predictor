
---

# 🌳 Income Classification with Decision Tree

This project builds a **Decision Tree Classifier** to predict whether an individual earns **more than \$50K** or **less than or equal to \$50K** annually based on demographic features from the [UCI Adult Income Dataset](https://archive.ics.uci.edu/ml/datasets/adult). It includes **data cleaning**, **exploratory analysis**, **model training**, **hyperparameter tuning**, and **feature importance visualization**.

---

## 📁 Dataset

- **Source:** [UCI Adult Income Dataset](https://archive.ics.uci.edu/ml/datasets/adult)
- **Records:** ~48,842
- **Target Variable:** `income` — Whether a person earns `<=50K` or `>50K` per year
- **Features:** Age, Education, Occupation, Marital Status, Hours per Week, etc.

---

## 🔧 Project Structure

```bash
📁 income-classifier/
│
├── data-cleaning.ipynb             # Initial data exploration and cleaning
├── data-dictionary.ipynb           # features and values meaning
├── DecisionTree-modeling.ipynb     # Full modeling workflow and visualizations
├── README.md                       # Project summary and documentation
```

---

## 🧹 Data Wrangling

Data was cleaned and processed with a custom `wrangle()` function that:
- Removes duplicates and missing values
- Drops irrelevant or skewed columns (`fnlwgt`, `education-num`, `capital-gain`, `capital-loss`)
- Converts target labels to binary (1 for `<=50K`, 0 for `>50K`)
- Filters out age outliers (limits age to ≤ 80)

---

## 📊 Exploratory Data Analysis

- Histograms, boxplots and bar charts were used to explore feature distributions
- Checked cardinality and correlation patterns
- Found that **`marital-status`** was the most predictive categorical feature

---

## 🌲 Model: Decision Tree Classifier

- **Encoding:** Ordinal encoding of categorical variables
- **Pipeline:** `OrdinalEncoder` → `DecisionTreeClassifier`
- **Validation Strategy:** 
  - Split data into Train (64%), Validation (16%), and Test (20%)
- **Metric:** Accuracy score

### 🔍 Model Evaluation

| Split       | Accuracy |
|-------------|----------|
| Train       | 83.01%   |
| Validation  | 81.64%   |
| Test        | 81.64%   |
| Baseline    | 75.22%   |

> ✅ Final model depth: **7**, determined by validation accuracy tuning

---

## 📈 Visualizations

### 🔹 Decision Tree Depth Tuning
A line chart was used to evaluate training and validation accuracy at various depths.

### 🔹 Decision Tree Plot
Tree plotted up to max depth of 3 to ensure interpretability.

### 🔹 Feature Importance
Top 3 most influential features:
- `marital-status`
- `occupation`
- `education`

![Feature Importance](https://via.placeholder.com/600x200?text=Feature+Importance+Plot)

---

## 🧰 Tools & Libraries

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- [ucimlrepo](https://pypi.org/project/ucimlrepo/) (for dataset fetch)

---
