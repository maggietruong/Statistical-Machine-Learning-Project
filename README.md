# 🏀 College Basketball Postseason Prediction
 
**Tools:** R, R Markdown, ggplot2, tidymodels, kknn, ranger, glmnet, kernlab

---

## 📌 Overview
This project uses **machine learning classification models** to predict whether a Division I NCAA basketball team will make the postseason — and, if so, how far they will advance.  
The analysis focuses on **offensive performance metrics** such as shooting percentages, turnover rates, and rebound rates.

The work was completed in **R Markdown** and includes **data cleaning, exploratory data analysis (EDA), visualization, and model comparison**.

---

## 🎯 Objectives
- Predict **Postseason Placement** based on six performance metrics.
- Compare multiple machine learning models to determine the best-performing approach.
- Use **visualizations** to explore data patterns and relationships.

---

## 📂 Dataset
- **Source:** Kaggle – *College Basketball Dataset* by Andrew Sundberg  
- **Years Covered:** 2013–2024  
- **Observations:** 3,523 teams  
- **Variables Used:**
  - `Three_Pointer` (3P_O) – % of successful three-point shots
  - `Free_Throw` (FTR) – Rate of free throw attempts
  - `Two_Pointer` (2P_O) – % of successful two-point shots
  - `Turnover` (TOR) – Turnover percentage allowed
  - `Rebound` (ORB) – Offensive rebound rate
  - `Field_Goal` (EFG_O) – Effective field goal percentage

---

## 🛠 Methods

### 1. Data Cleaning
- Replaced `NA` postseason values with `"No Postseason"`.
- Selected only the predictor variables and target (`POSTSEASON`).

### 2. Exploratory Data Analysis (EDA)
- **Bar Chart:** Distribution of postseason placements.
- **Boxplots:** Free throw vs. three-point shooting by postseason rank.
- **Correlation Heatmap:** Relationships among predictors.
- **Scatterplot Matrix:** Trends between shooting metrics and postseason outcomes.

### 3. Model Creation & Comparison
Four untuned models were initially tested:
- **Logistic Regression** (`glmnet`)
- **K-Nearest Neighbors (KNN)** (`kknn`)
- **Random Forest** (`ranger`)
- **Support Vector Machine (SVM)** (`kernlab`)

**Metrics Used:**
- **AUC** (Area Under the ROC Curve)
- **Error Rate** (1 - Accuracy)

---

## 📊 Results

| Model                  | AUC     | Error Rate |
|------------------------|---------|------------|
| Logistic Regression    | 0.5000  | 0.1979     |
| K-Nearest Neighbors    | 0.9985  | **0.0689** |
| Random Forest          | **0.9992** | 0.0860     |
| Support Vector Machine | 0.6434  | 0.1971     |

**Best Model:**  
- **KNN** chosen for lowest error rate (0.0689), despite Random Forest having a slightly higher AUC.

**Tuning:**  
- Cross-validation determined optimal `k = 29` for KNN.
- Tuned KNN achieved AUC = 0.9106, Error Rate = 0.176.

---

## 📌 Conclusion
- Offensive metrics can be strong predictors of postseason success.
- KNN and Random Forest performed best; Logistic Regression performed worst.
- Future improvements could include:
  - Adding more predictors (e.g., Power Rating, Adjusted Offensive Efficiency).
  - Investigating misclassified teams to refine model accuracy.

---

## 📷 Sample Visualizations

**Postseason Placement Distribution**
![postseason-bar](images/postseason_bar.png)

**Free Throws vs. Three Pointers by Postseason Rank**
![boxplot](images/boxplot.png)

**Correlation Heatmap**
![heatmap](images/heatmap.png)

---

## 🚀 How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/Statistical-Machine-Learning-Project.git
