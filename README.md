#  HR Analytics with PCA

This project explores an **HR dataset** containing employee information such as demographics, performance, engagement, satisfaction, salary, and absenteeism.  
We apply data cleaning, visualization, and **Principal Component Analysis (PCA)** to extract insights and reduce complexity.

---

##  Project Overview

The project follows this pipeline:

1. **Data Cleaning & Preprocessing**
2. **Exploratory Data Analysis (EDA)**
3. **Feature Engineering**
4. **Dimensionality Reduction with PCA**
5. **Visualization & Insights**

---

## 1. Data Cleaning

- Loaded the dataset (`HRDataset_v14.csv`).
- Removed or handled:
  - **Missing values** in engagement survey, satisfaction scores, etc.
  - **Duplicate rows** if any.
- Dropped irrelevant identifiers (e.g., `EmpID`, `ManagerID`, `DeptID`) that don’t add value to PCA.
- Encoded categorical variables if needed for modeling.

---

## 2. Exploratory Data Analysis (EDA)

- **Distribution Analysis**:
  - Histograms of salary, absenteeism, satisfaction scores.
- **Comparisons**:
  - Average salary by gender (boxplot).
  - Satisfaction by department (barplot).
  - Employee terminations over time (time series plot).
- **Correlations**:
  - Heatmap of numeric features to identify strong relationships.

---

## 3. Feature Engineering

- Created subsets of data for analysis:
  - Engagement-related features: `EngagementSurvey`, `EmpSatisfaction`, `Absences`.
  - Performance & salary analysis features.
- Standardized numeric features using **`StandardScaler`** (important for PCA, since features are on different scales).

---

## 4. Principal Component Analysis (PCA)

- Applied PCA on standardized numeric features.
- Examined **explained variance ratio** to decide how many components to keep.
- Interpreted the first two principal components:
  - **PC1**: Captures overall employee engagement/morale patterns.
  - **PC2**: Captures contrasts between absenteeism and satisfaction.
- Reduced dataset to **2D** with PCA for visualization.

---

## 5. Visualization & Insights

- **Explained Variance Plot**: Shows how much variance each PC explains.
- **2D PCA Projection**:
  - Employees plotted in PCA space, colored by department or performance score.
- **Loadings Plot**:
  - Visualizes how `Salary`, `Absences`, and `EngagementSurvey` contribute to PC1 and PC2.
- **Clustering Comparison**:
  - K-Means clustering before and after PCA to evaluate dimensionality reduction effects.

---

## 4. Key Insights

- Engagement and satisfaction scores are **highly correlated**, while absences provide an opposite signal.
- PCA reduces correlated survey and performance metrics into fewer **latent factors**, making them easier to interpret.
- Visualization in PCA space highlights differences between **departments** and **performance groups**.
- PCA can simplify survey analysis by condensing dozens of questions into a few meaningful dimensions.

