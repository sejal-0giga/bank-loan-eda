# bank-loan-eda
Bank Loan Default Risk Analysis using Python
# Bank Loan Default Risk Analysis (Python EDA)

## 📌 Project Overview
This project focuses on analysing bank loan data to understand approval trends and default risk.  
EDA is performed using **Python (Pandas, NumPy, Matplotlib)**.

## 🎯 Objectives
- Analyse loan approval vs rejection patterns  
- Study default behaviour across credit scores  
- Compare risk between salaried and self-employed customers  
- Explore regional (property area) level risk  
- Understand relationship between income and loan amount  

## 📂 Dataset
- 500 rows, 14 columns
- Key columns:
  - `Age`, `Annual_Income`, `Loan_Amount`, `Loan_Tenure`
  - `Gender`, `Marital_Status`, `Employment_Type`
  - `Credit_Score`, `Property_Area`
  - `Loan_Status` (Approved / Rejected)
  - `Default_Flag` (Yes / No)

## 🛠 Tech Stack
- Python
- Pandas, NumPy
- Matplotlib
- Jupyter Notebook

## 🔍 Key EDA Steps
1. Data loading and structure understanding  
2. Missing value and data type checks  
3. Summary statistics for numeric features  
4. Loan approval vs rejection analysis  
5. Default analysis by:
   - Credit Score  
   - Employment Type  
   - Property Area  
6. Income vs Loan Amount scatter analysis  

## 📊 Insights Summary
- Loan approval rate is around ~52%, rejections ~48%, indicating a balanced risk policy.
- Customers with **Credit Score C** show the highest number of defaults.
- **Self-employed** customers have a slightly higher default count compared to salaried.
- Defaults are relatively higher in **Urban and Semi-Urban** property areas.
- Income and loan amount show a weak positive correlation; some low-income customers still receive high loan amounts, indicating potential risk.

## 🚀 How to Run
1. Clone the repository  
2. Place `bank_loan_dataset.csv` in the project folder  
3. Open Jupyter Notebook  
4. Run `bank_loan_eda.ipynb` cell by cell  

## 📌 Future Work
- Build a classification model to predict loan default  
- Add interactive dashboards using Power BI / Streamlit
