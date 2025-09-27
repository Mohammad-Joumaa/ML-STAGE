# Task 1 – Student Score Prediction

In this task, I worked on predicting student exam scores using the **Student Performance Factors** dataset from [Kaggle](https://www.kaggle.com/datasets/lainguyn123/student-performance-factors). The goal was to analyze the main factors that affect performance and compare different machine learning models.

---

## Project Workflow

* **Data Loading & Cleaning** – imported the dataset (or generated a synthetic version if missing).
* **Exploratory Data Analysis** – studied distributions, correlations, and visual patterns.
* **Feature Engineering** – encoded categorical variables and prepared features for modeling.
* **Modeling** – trained and compared:

  * Simple Linear Regression
  * Multiple Linear Regression
  * Polynomial Regression
  * Random Forest Regressor
* **Evaluation** – compared R², RMSE, and MAE across all models.
* **Insights & Recommendations** – summarized key factors for student success.

---

## Results

| Model                         | R² Score | Notes                       |
| ----------------------------- | -------- | --------------------------- |
| Simple Linear Regression      | ~0.55    | Weak baseline               |
| Multiple Linear Regression    | ~0.72    | Better fit                  |
| Polynomial Regression (deg 3) | ~0.75    | Captures non-linear effects |
| **Random Forest (Best)**      | **0.89** | Best performance            |

👉 The **Random Forest model** explained around **89% of the variance** in exam scores, making it the most reliable approach in this task.

---

## Key Insights

* **Hours Studied** and **Previous Scores** are the strongest predictors.
* **Parental Involvement** and **Access to Resources** play an important role.
* **Healthy sleep (7–8 hrs)** shows a positive impact on performance.
* Tutoring and private schooling also showed consistent improvements in scores.

---

## Dataset

* **Name:** Student Performance Factors
* **Source:** [Kaggle](https://www.kaggle.com/datasets/lainguyn123/student-performance-factors)
* **Target Variable:** `Exam_Score`

---

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/Mohammad-Joumaa/ML-STAGE.git
   cd ML-STAGE
   ```
2. Open the notebook:

   ```bash
   jupyter notebook Task1_Student_Score_Prediction.ipynb
   ```
3. Run all cells to reproduce the analysis.

---

## Conclusion

This project highlights how machine learning can be used to **identify the most important factors in student success** and provide actionable insights for both students and educators.

# Task 2 – Mall Customer Segmentation 🛍️

In this task, I performed **customer segmentation analysis** using the classic **Mall Customer dataset** (simulated based on [Kaggle’s dataset](https://www.kaggle.com/datasets)). The main goal was to group mall customers into meaningful clusters based on their **income** and **spending behavior**, which can help businesses design targeted marketing strategies.

---

## Project Workflow

* **Data Preparation** – generated a synthetic dataset with customer demographics, income, and spending scores.
* **Exploratory Data Analysis (EDA)** – distributions, correlations, and visualizations to understand patterns.
* **Feature Engineering** – focused on `Annual Income` and `Spending Score`, scaled features for clustering.
* **Clustering Models**

  * **K-Means Clustering** – used Elbow method and Silhouette score to determine the optimal number of clusters.
  * **DBSCAN** – tested as an alternative density-based approach.
* **Cluster Analysis** – interpreted segments (e.g., premium customers, conservative customers, impulse buyers, etc.).
* **Business Insights** – linked clusters to actionable marketing strategies.

---

## Results

✅ **Optimal number of clusters:** 5 (from Silhouette score analysis)
✅ **Best algorithm:** K-Means (clear separation of customer groups)
✅ **DBSCAN** found fewer clusters but highlighted outliers/noise

---

## Cluster Interpretation

* **Cluster 0 – High Income, High Spending** → Premium customers, ideal for luxury targeting.
* **Cluster 1 – High Income, Low Spending** → Conservative customers, need value-based offers.
* **Cluster 2 – Low Income, High Spending** → Impulse buyers, can be engaged with promotions.
* **Cluster 3 – Low Income, Low Spending** → Budget-conscious customers, suited for discounts.
* **Cluster 4 – Balanced Segment** → Average customers with moderate spending.

---

## Key Insights for Business

* Focus **premium customers** with exclusive luxury products.
* Encourage **conservative customers** with loyalty rewards and personalized offers.
* Offer **budget-friendly options** to price-sensitive customers.
* Design **promotions** for impulse buyers to increase basket size.

---

## Technical Details

* **Features used:** Annual Income, Spending Score
* **Preprocessing:** Standard scaling applied
* **Validation:** Elbow method & Silhouette score
* **Clustering algorithms:** K-Means (main), DBSCAN (alternative)

---

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/Mohammad-Joumaa/ML-STAGE.git
   cd ML-STAGE
   ```
2. Open the notebook:

   ```bash
   jupyter notebook Task2_CustomerS.ipynb
   ```
3. Run all cells to reproduce results and visualizations.

---

## Conclusion

Customer segmentation is a powerful tool for businesses to **understand customer behavior** and create **targeted marketing strategies**. K-Means clustering successfully identified five distinct customer groups, providing clear directions for business decision-making.

# Task 3 – Forest Cover Type Classification 🌲

This project tackles a **multi-class classification problem** using the **Covertype dataset** from the UCI Machine Learning Repository. The goal is to predict the **type of forest cover** (7 classes) based on **cartographic and environmental features** such as elevation, slope, soil type, and distances to hydrology, roadways, and fire points.

---

## Project Workflow

* **Data Acquisition**

  * Downloaded the Covertype dataset from UCI (with fallback synthetic data if unavailable).
  * 581k+ samples, 54 features, and 7 target classes.

* **Data Exploration & Cleaning**

  * Checked distributions, correlations, and target class balance.
  * Verified categorical (wilderness, soil type) and numerical features.

* **Preprocessing**

  * Scaled numerical features with `StandardScaler`.
  * Ensured binary encoding for categorical features.

* **Model Training**

  * **Random Forest Classifier** (baseline).
  * **XGBoost** (or Gradient Boosting if XGBoost not available).
  * Hyperparameter tuning with `GridSearchCV`.

* **Evaluation**

  * Accuracy comparison across models.
  * Confusion matrix & classification report.
  * Per-class accuracy and cross-validation analysis.

* **Feature Importance**

  * Identified the most influential features (elevation was consistently top).

---

## Results

| Model             | Accuracy |
| ----------------- | -------- |
| Random Forest     | ~0.93    |
| XGBoost / GB      | ~0.92    |
| Final Tuned Model | ~0.94    |

* Cross-validation mean score: **0.935 ± 0.005**
* Elevation, soil type, and hydrology distances were among the most important predictors.

---

## Key Insights

* **Elevation** is the single most important factor in forest cover type prediction.
* Soil types and hydrological features also play significant roles.
* Random Forest slightly outperformed boosting models in this setup.
* Hyperparameter tuning improved accuracy by ~1–2 percentage points.

---

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/Mohammad-Joumaa/ML-STAGE.git
   cd ML-STAGE
   ```
2. Open the notebook:

   ```bash
   jupyter notebook Task3_Forest.ipynb
   ```
3. Run all cells to download the dataset, preprocess, train models, and evaluate results.

---

## Conclusion

This project demonstrates how machine learning can be applied to **ecological and environmental modeling**, with strong predictive accuracy across multiple forest cover types. The workflow includes a **complete ML pipeline**: preprocessing, model training, hyperparameter tuning, cross-validation, and feature analysis.

# Task 4 – Loan Approval Prediction 🏦

This project focuses on predicting **loan approval status** for applicants using a machine learning pipeline. The dataset is based on the **Loan Prediction dataset from Kaggle**, but in this notebook, I generated a **synthetic dataset** that closely matches the real-world structure.

The objective is to build a model that can help financial institutions **assess the risk of loan applications** by analyzing applicant demographics, financial history, and credit information.

---

## Project Workflow

* **Synthetic Dataset Creation**

  * Generated ~600 loan application records with realistic distributions.
  * Included missing values for realism.

* **Exploratory Data Analysis (EDA)**

  * Distribution plots for loan approval, gender, education, income, and loan amounts.
  * Correlation analysis between features and target variable.

* **Data Preprocessing**

  * Handled missing values (mode for categorical, median for numeric).
  * Encoded categorical variables with Label Encoding.
  * Created new features:

    * `Total_Income` (Applicant + Coapplicant)
    * `Income_Loan_Ratio` (affordability indicator)
    * `Monthly_Payment` (loan amount vs term).
  * Scaled numerical features using `StandardScaler`.
  * Applied **SMOTE** to handle class imbalance.

* **Model Training**

  * Logistic Regression
  * Decision Tree
  * Random Forest (baseline and tuned with GridSearchCV).

* **Evaluation Metrics**

  * Accuracy, Precision, Recall, F1-score
  * Confusion matrices
  * Cross-validation for robustness

* **Hyperparameter Tuning**

  * Grid search on Random Forest to optimize depth, estimators, and splits.

* **Final Deployment-Ready Model**

  * Best model: **Random Forest**
  * Wrapped in a custom function `predict_loan_approval()` for new applicant predictions.

---

## Results

| Model               | Accuracy  | Precision | Recall   | F1-Score |
| ------------------- | --------- | --------- | -------- | -------- |
| Logistic Regression | ~0.79     | ~0.77     | ~0.81    | ~0.79    |
| Decision Tree       | ~0.82     | ~0.80     | ~0.83    | ~0.82    |
| **Random Forest**   | **0.85+** | **0.84**  | **0.86** | **0.85** |

* After hyperparameter tuning, **Random Forest** achieved the best balance of recall and precision.
* Feature importance analysis highlighted:

  * **Credit History** as the most significant predictor.
  * **Total Income** and **Loan Amount** as strong secondary features.

---

## Business Insights

* Applicants with **good credit history** and **higher income-to-loan ratios** are more likely to be approved.
* Loan prediction models can **reduce manual processing** and **speed up decision-making** in financial institutions.
* Such models can be used as **supporting tools** for loan officers rather than complete replacements.

---

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/Mohammad-Joumaa/ML-STAGE.git
   cd ML-STAGE
   ```
2. Open the notebook:

   ```bash
   jupyter notebook Task4_Loan.ipynb
   ```
3. Run all cells to train the model and test predictions.

---

## Conclusion

This project demonstrates how machine learning can help in **loan risk assessment**. By combining preprocessing, feature engineering, and model training, the final model can **predict loan approval with high confidence** and is ready for **deployment in real-world systems**.



