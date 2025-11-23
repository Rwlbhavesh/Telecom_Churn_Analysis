# Telecom Customer Churn Prediction using Machine Learning

## 1. Project Overview

This project focuses on leveraging data analysis and Machine Learning (ML) techniques to predict customer churn within the telecom industry. The telecom sector frequently experiences **high customer churn** due to intense competition and frequent price switching.

The primary goal is to analyze customer behavior, identify key factors driving attrition, and build a reliable prediction model. This system is designed to **support targeted retention campaigns**, reduce customer loss, and ultimately improve the business performance of No-Churn Telecom.

## 2. Dataset Summary

The analysis was performed on a comprehensive dataset containing detailed customer information.

| Metric | Detail | Source |
| :--- | :--- | :--- |
| **Record Count** | **4,617** customer records | |
| **Data Type** | Telecom Customer Usage Dataset | |
| **Target Variable** | Churn (True/False), converted to **CHURN\_FLAG (1/0)** | |

**Key Data Categories Contained:**

*   **Customer Details:** State, Account Length, Area Code.
*   **Plan Details:** International Plan (Yes/No), Voice Mail Plan, Voice Mail Messages.
*   **Usage Metrics:** Day/Evening/Night/International Minutes, Calls, and Charges.
*   **Customer Experience:** **Number of Customer Service Calls**.

## 3. Methodology and Workflow

The project followed a structured approach involving data preparation, feature engineering, and Machine Learning modeling.

### 3.1 Data Preparation (Excel)

Data preparation was crucial for ensuring data quality.

*   The dataset was imported into Excel.
*   The `Churn` column was cleaned and standardized.
*   All minute, call, and charge fields were **converted into numeric format**.
*   The target variable, **CHURN\_FLAG**, was created.
*   Categorical features (Yes/No plans) were standardized to 1/0.

### 3.2 Feature Engineering

New features were created to enhance pattern recognition for the ML model:

*   **`Total_mins`**: Sum of Day + Eve + Night + International Minutes.
*   **`Total_charge`**: Total Charges across all time periods.
*   **`Avg_day_call_duration`**: Calculated as Day Minutes / Day Calls.
*   A basic manual risk logic was also applied to understand initial patterns.

### 3.3 Exploratory Data Analysis (EDA)

EDA identified critical churn drivers:

*   Overall Churn Rate ≈ **14%**.
*   **Strong Correlation:** Customers with **more customer service calls** exhibited significantly higher churn rates.
*   Usage and charges were strongly linked to churn.

### 3.4 Machine Learning Modeling (Orange Data Mining Tool)

The **Orange Data Mining Tool** was used to compare multiple ML algorithms.

**Models Applied:** Logistic Regression, Random Forest, and Decision Tree.

**Workflow in Orange:**
The cleaned dataset is imported (CSV File Import widget). Features and the target variable (`CHURN_FLAG`) are defined (Select Columns widget). Feature importance is evaluated using the **Rank widget**. Models are connected to the **Test & Score widget** to compare metrics (AUC, Accuracy). The best model generates churn probabilities (**Risk Scores**) using the **Predictions widget**.

## 4. Key Results and Model Performance

### 4.1 Optimal Model

*   **Best Model:** **Random Forest**.
*   **Highlights:** Delivered the best AUC (Area Under the Curve) and demonstrated strong prediction stability and balanced performance on both churn and non-churn customers.

### 4.2 Confusion Matrix Output

The model proved reliable for identifying potential churners.

| Prediction Result | Count |
| :--- | :--- |
| True Non-Churn | **3958** |
| True Churn | **580** |
| Missed Churn (False Negatives) | **76** |
| Wrong Churn Prediction (False Positives) | **3** |

### 4.3 Risk Segmentation

The ML-generated probability scores were exported and segmented to create an **actionable retention roadmap**.

*   The generated **risk score** effectively identifies customers most likely to churn.
*   **Example Segmentation:** High Risk (≥ 70), Medium Risk (70–40), and Low Risk (< 40).

## 5. Conclusion and Recommendations

### 5.1 Final Insights

*   **Complaint Frequency** (Customer Service Calls) is the **strongest identified churn driver**.
*   The ML model successfully established an analytical framework for proactive customer retention.
