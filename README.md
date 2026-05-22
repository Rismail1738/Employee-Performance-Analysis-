# Employee Performance Analysis

This project analyses employee data from a company called INX Future Inc. to
understand what drives employee performance and to build a model that can
predict an employee's performance rating.

## Background

INX Future Inc. is a data analytics and automation company. In recent years its
employee performance had been declining, service delivery escalations were
rising, and client satisfaction had dropped by around 8 percentage points. The
goal of this project is to find the real causes behind this using the company's
employee data, and to build a model that can support better hiring decisions.

## Objectives

1. Analyse performance department by department.
2. Identify the top 3 factors that affect employee performance.
3. Build a model that can predict an employee's performance rating.
4. Provide practical recommendations to improve performance.

## Dataset

- 1,200 employees and 28 columns, with no missing values.
- Target variable: `PerformanceRating` (2 = Low, 3 = Good, 4 = Excellent).
- The data is imbalanced, with most employees rated as Good performers.

## Approach

The full analysis is contained in a single Jupyter notebook and follows these steps:

1. **Data exploration** — shape, data types, missing values and statistical summary.
2. **Exploratory Data Analysis** — target distribution, department performance,
   a correlation heatmap, boxplots, distribution plots, and charts comparing
   performance against overtime, attrition, gender, marital status, job role
   and education.
3. **Outlier detection** using the interquartile range (IQR) method.
4. **Preprocessing** — Label Encoding for the text columns and removing the ID column.
5. **PCA check** — used to decide whether dimensionality reduction was worthwhile
   (it was not, since 22 of 26 components were needed to keep 95% of the variance).
6. **Modelling** — three classification models trained and compared:
   Random Forest, Gradient Boosting and Logistic Regression.
7. **Validation and tuning** — a stratified train/test split, 5-fold cross
   validation, and GridSearchCV for hyperparameter tuning.
8. **Evaluation** — accuracy, precision, recall, F1 score, confusion matrices
   and ROC/AUC curves.
9. **Feature importance** and final recommendations.

## Key Results

**Best model:** Random Forest — about 93.75% accuracy (cross-validated at 93.58%).

| Model | Test Accuracy |
| --- | --- |
| Random Forest | 93.75% |
| Gradient Boosting | 92.92% |
| Logistic Regression | 73.75% |

**Top 3 factors affecting performance:**

1. Last salary hike percentage
2. Environment satisfaction
3. Years since last promotion

**Department performance:** Development and Data Science were the strongest,
while Finance and Sales were the weakest and need the most attention.

## Repository Structure
.
├── data/
│   └── INX_Future_Inc_Employee_Performance_Data.xls
├── notebook/
│   └── INX_Employee_Performance_Analysis.ipynb
├── summary/
│   └── INX_Project_Summary.docx
├── requirements (1).txt
└── README.md
## How to Run

1. Clone the repository:
```bash
   git clone https://github.com/Rismail1738/Employee-performance-Analysis.git
   cd Employee-performance-Analysis
```
2. Install the required libraries:
```bash
   pip install -r requirements(1).txt
```
3. Launch Jupyter:
```bash
   jupyter notebook
```
4. Open the notebook and run all cells from top to bottom.

> Note: the dataset is an older `.xls` file, which is why `xlrd` is included in
> the requirements(1). Make sure the data file path in the notebook points to
> where you have saved the data.

## Tools Used

Python, Jupyter Notebook, pandas, numpy, matplotlib, seaborn, scikit-learn.
