# Predicting-Product-Success-Loyalty-Based-Targeting-for-Optimal-Market-Penetration
This project demonstrates how marketing analytics powered by machine learning can significantly optimize campaign performance by targeting only the most probable buyers. In real-world business environments where marketing budgets are limited, such approaches can help maximize ROI while reducing operational costs.

-----

## 🧠 Problem Statement

A business plans to promote a new product to loyalty program members. Due to a limited marketing budget, it can only reach out to a portion of them. This project answers:

> “Can we use data-driven methods to identify the customers most likely to buy, and optimize our outreach accordingly?”

---

## 📁 Project Structure

```text
├── a1_Dataset_10Percent.xlsx        # 10% customer sample (used for model training)
├── a2_Dataset_90Percent.xlsx        # Remaining 90% dataset (used for prediction)
├── b1_Marketing_Campaign.ipynb      # Notebook for EDA, preprocessing, model building
├── b2_Predictor_Marketing.ipynb     # Notebook for scoring 90% customers & decile analysis
├── Predicting Product Success.pptx  # Presentation summarizing the business impact
```

-----

## 📘 Learning Outcomes

- How to clean and prepare real-world marketing data
- How to handle missing values using **mean/mode imputation**
- How to encode categorical variables using **label encoding**
- Build and evaluate a **Logistic Regression classifier**
- Understand and apply **Decile Analysis** for campaign strategy
- Translate model outputs into **business insights and ROI impact**

---

## 📊 Dataset Description

The Excel files represent customer data from a loyalty program, split into:

- **10% Sample** for model training
- **90% Holdout** for applying predictions

### Common Features:
- Demographics (e.g., age, gender, region)
- Loyalty behavior (e.g., length of membership)
- Purchase patterns

### Target:
- `TargetBuy`: Whether the customer is likely to buy (`1`) or not (`0`)

---

## 📒 Notebook Breakdown

### ✅ `b1_Marketing_Campaign.ipynb` — Training Phase

This notebook handles:

1. **Importing and Exploring Data**
   - Loads the 10% sample dataset  
   - Drops customer `ID` column  
   - Checks and summarizes null values

2. **Data Cleaning & Imputation**
   - Fills missing values using `mode()` for categorical variables  
   - Uses `mean()` for numeric columns like `LoyalTime`

3. **Feature Encoding**
   - Converts categorical columns into numerical format using **Label Encoding**

4. **Train-Test Split & Scaling**
   - Splits data into training/testing sets  
   - Applies **StandardScaler** to standardize features

5. **Model Building**
   - Trains a **Logistic Regression** classifier  
   - Evaluates model using:
     - **Accuracy Score**
     - **Confusion Matrix**
     - **Classification Report**

6. **Results**
   - Achieved ~**81% accuracy** on test data  
   - Model is saved for future use on the 90% dataset

---

### ✅ `b2_Predictor_Marketing.ipynb` — Scoring & Strategy

This notebook handles:

1. **Loading Model & New Data**
   - Loads the previously trained model  
   - Imports the 90% loyalty base dataset

2. **Data Cleaning**
   - Applies the same imputation rules as in the training phase  
   - Encodes categorical variables using Label Encoding  
   - Scales the data using the same `StandardScaler`

3. **Prediction & Probability Scoring**
   - Applies the model to predict **probabilities of purchase** for each customer  
   - Sorts the customers based on predicted probability

4. **📊 Decile Analysis**
   - Divides the sorted probabilities into **10 equal groups (deciles)**  
   - **1st decile = most likely to buy**, **10th decile = least likely**

5. **📈 Strategic Options Analyzed**
   - **No Model**: Random targeting of customers  
   - **Market Penetration Strategy**: Target top 50% of customers  
   - **Profit Maximization Strategy**: Target top 30% only

6. **Business Impact Modeling**
   - Revenue per conversion: `$15,000`  
   - Cost per sample kit: `$4,420`  
   - Calculates cost-revenue tradeoffs across strategies  
   - Identifies optimal targeting deciles to **maximize profitability** and **minimize spend**

---

## 📌 Concepts Used

- **Logistic Regression** for binary classification  
- **Standardization** for model stability  
- **Label Encoding** for categorical data  
- **Missing Value Imputation** using mean/mode  
- **Probability Ranking** for prioritization  
- **Decile Analysis** for marketing segmentation  
- **Cost-Benefit Analysis** for business impact assessment

---

## 📈 Results Snapshot

| Metric                          | Value              |
|---------------------------------|--------------------|
| Model Accuracy                  | ~81%               |
| Revenue per Converted Customer  | $15,000            |
| Cost per Sample Kit             | $4,420             |
| Most Profitable Strategy        | Target Top 3 Deciles |
| Tool for Prioritization         | Decile Methodology |
| Model Type                      | Logistic Regression |

---

## 💡 Key Takeaways

- Predictive modeling improves targeting precision and ROI.
- Decile segmentation enables informed marketing decisions at scale.
- Significant cost savings are achieved by avoiding low-probability leads.

---

## ⚙️ How to Run Locally

### 1. Clone the Repository

```bash
git clone https://github.com/Bsetia1/Predicting-Product-Success-Loyalty-Based-Targeting-for-Optimal-Market-Penetration.git
cd Predicting-Product-Success-Loyalty-Based-Targeting-for-Optimal-Market-Penetration
```

### 2. Install Required Libraries
You can install the dependencies using pip and the provided requirements.txt:

```bash
pip install -r requirements.txt
```
Or manually install them:

```bash
pip install pandas numpy scikit-learn openpyxl matplotlib
```
💡 Make sure you're using Python 3.7 or above.

### 3. Run the Notebooks
Open the notebooks using Jupyter or VSCode:

Run b1_Marketing_Campaign.ipynb to train and evaluate the model

Run b2_Predictor_Marketing.ipynb to predict and analyze targeting strategies




### 👩‍💻 Author
Bhavya Setia
Data Analytics | Marketing Strategy | Machine Learning

[LinkedIn](https://www.linkedin.com/in/bhavyasetia341)
