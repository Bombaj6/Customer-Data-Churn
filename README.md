## 📌 Project Summary

The goal of this project was to **predict customer churn** using historical data from a telecommunications company. By identifying customers at risk of leaving, the business can take proactive measures to retain them and reduce revenue loss.

### 🎯 Objective
- Predict whether a customer will churn (leave) or stay
- Support business decisions around customer retention

### 📊 Dataset Overview
The dataset includes customer demographics, account details, and service usage features such as:
- `CustomerID`, `Gender`, `SeniorCitizen`
- `Contract`, `Tenure`, `MonthlyCharges`, `TotalCharges`
- `InternetService`, `PaymentMethod`, etc.
- Target: `Churn` (1 = left, 0 = stayed)

### 🧠 Techniques & Tools Used
- Python: `pandas`, `seaborn`, `scikit-learn`, `imblearn`
- Data cleaning, encoding, and scaling
- EDA and feature importance analysis
- Modeling with Random Forest
- Class imbalance handling with SMOTE and class weights
- Threshold tuning for better recall

---

## 📊 Exploratory Data Analysis (EDA)

### 🔍 Data Cleaning
- Converted `TotalCharges` to numeric and handled missing values
- Encoded categorical variables
- Checked for imbalance in the target variable

### 📉 Churn Insights
- ~26% of customers churned
- Higher churn among:
  - Month-to-month contracts
  - Fiber optic users
  - Customers paying with electronic checks
  - Short tenure customers

### 🔢 Feature Importance
Top predictors of churn:
1. `SeniorCitizen`
2. `Contract`
3. `InternetService`
4. `PaymentMethod`

---

## 🛠️ Model Development & Evaluation

### ✅ Baseline Model (Random Forest)
- Accuracy: **0.67**
- Churn Recall: **0.06** (very low)

### ⚖️ Class Weight Adjustment
- Accuracy: **0.69**
- Churn Recall: **0.12**
- Churn Precision: **0.57**

### 🔁 SMOTE
- Accuracy: **0.58**
- Churn Recall: **0.28**
- Churn Precision: **0.32**

### 🎯 Threshold Tuning (Threshold = 0.3)
- Accuracy: **0.43**
- Churn Recall: **0.66**
- Churn Precision: **0.31**

### 🧠 Final Model Choice
**Random Forest with class weight and threshold tuning**
- Best balance of recall and precision for business value
- Prioritizes identifying churners for proactive intervention

---

## 🏁 Conclusion & Recommendations

We built a churn prediction model that effectively identifies customers likely to leave. While the overall accuracy is modest due to class imbalance, the model performs well in detecting churners, which aligns with business goals.

### ✅ Key Takeaways
- High-risk segments include: short tenure, month-to-month contracts, fiber optic users, and electronic check payers
- Model recall improved from **6% → 66%** with threshold tuning

### 💼 Business Recommendation
- Use this model to flag churn-prone customers
- Focus retention strategies (discounts, outreach) on high-risk groups
- Monitor model predictions monthly to guide marketing efforts

### 🔮 Future Improvements
- Try advanced models like XGBoost or LightGBM
- Incorporate customer support/satisfaction data
- Deploy the model for real-time churn alerts

---

