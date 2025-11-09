# Customer Churn Prediction using Logistic Regression

This project analyzes **customer churn behavior** for a telecom company using **Logistic Regression**.  
The objective is to identify customers most likely to leave and propose **data-driven strategies** to improve customer retention.

---

## Objective

To build a predictive model that classifies customers as likely to churn or not, understand key influencing factors, and generate **business recommendations** based on model insights.

---

## Files in This Repository

| File Name | Description |
|------------|--------------|
| `Logistic_regression.ipynb` | Jupyter Notebook containing the full analysis, model building, and evaluation workflow |
| `churn.csv` | Dataset used for churn prediction |
| `requirements.txt` | Python dependencies required to run the notebook |
| `README.md` | Project summary, insights, and business recommendations |

---

## Dataset Description

**Dataset:** `churn.csv`  
**Records:** ~7,000 customer entries  
**Source:** Telco Customer Churn Dataset  

| Feature | Description |
|----------|--------------|
| `gender` | Male or Female |
| `SeniorCitizen` | Whether the customer is a senior citizen |
| `Partner`, `Dependents` | Relationship indicators |
| `tenure` | Months the customer has stayed |
| `PhoneService`, `InternetService` | Service usage details |
| `Contract` | Contract type (Month-to-month, One year, Two year) |
| `PaymentMethod` | Billing method |
| `MonthlyCharges` | Monthly payment |
| `TotalCharges` | Total amount billed |
| `Churn` | Target variable (Yes = churned, No = retained) |

---

## Workflow

### **1. Data Cleaning**
- Handled missing values in `TotalCharges`
- Converted categorical churn values (“Yes” / “No”) to binary (1 / 0)

### **2. Feature Selection**
- Focused on the key numeric predictors:
  - `tenure`
  - `MonthlyCharges`
  - `SeniorCitizen`

### **3. Data Splitting**
- Split the dataset into:
  - **Training Set:** 70%
  - **Testing Set:** 30%
- Used `train_test_split` for reproducibility

### **4. Model Building**
- Applied **Logistic Regression** using `scikit-learn`
- Model trained to predict `Churn` (binary classification)

### **5. Model Evaluation**
- Evaluated performance with:
  - **Confusion Matrix**
  - **Accuracy Score**
  - **Precision, Recall, F1-Score**

---

## Model Performance

| Metric | Non-Churn (0) | Churn (1) |
|---------|----------------|-----------|
| **Precision** | 0.82 | 0.66 |
| **Recall** | 0.91 | 0.46 |
| **F1-Score** | 0.87 | 0.54 |
| **Accuracy** | **0.79 overall** |


---

## Key Insights

| Factor | Impact on Churn |
|---------|----------------|
| **Tenure** | Longer tenure = lower likelihood of churn |
| **MonthlyCharges** | Higher monthly bills = increased churn risk |
| **SeniorCitizen** | Slightly higher churn tendency due to service complexity or cost sensitivity |

---

## Business Recommendations

### **1. Focus on Retaining New Customers**
- Low-tenure customers are most likely to leave.  
- Offer early loyalty rewards, onboarding support, and personalized engagement in the **first 3–6 months**.

---

### **2. Reassess High Monthly Charge Plans**
- Customers with high monthly charges show higher churn.  
- introduce **tiered pricing**, **bundle offers**, or **discounts** for long-term customers.

---

### **3. Simplify Offers for Senior Citizens**
- Senior customers may struggle with complex plans or digital platforms.  
- Launch **senior-friendly plans** with simplified billing and dedicated support.

---

### **4. Implement Predictive Retention Strategies**
- Integrate the model into a **churn prediction dashboard** to score customers monthly.
- Use churn probability to trigger retention campaigns or customer service follow-ups.

---

### **5. Segment Retention Actions**
Use churn probability scores for personalized marketing:

| Risk Level | Probability Range | Action |
|-------------|------------------|--------|
| **High Risk** | ≥ 0.7 | Personalized offers, direct contact |
| **Medium Risk** | 0.4–0.7 | Loyalty rewards, engagement campaigns |
| **Low Risk** | < 0.4 | Routine satisfaction checks |

---

## Learning Reflection

> “This project taught me how to apply logistic regression to a real business problem, evaluate performance critically, and connect model outputs with strategic decisions.  
While the recall for churners is moderate (46%), the project emphasizes **actionable business insights** and opportunities to enhance model performance using richer data.
