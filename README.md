# bank-loan-eda
Bank Loan Default Risk Analysis using Python
# -------------------------
# 1. IMPORT LIBRARIES
# -------------------------
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# For better display (optional)
pd.set_option('display.max_columns', None)

# -------------------------
# 2. LOAD DATA
# -------------------------
df = pd.read_csv("C:/Users/Sejal/Downloads/bank_loan_dataset.csv")
df.head()

# -------------------------
# 3. BASIC INFO
# -------------------------
df.shape          # rows, columns
df.info()         # data types & non-null counts
df.columns        # column names

# -------------------------
# 4. MISSING VALUES CHECK
# -------------------------
df.isnull().sum()

# -------------------------
# 5. SUMMARY STATISTICS
# -------------------------
df.describe()   # only numerical columns

# -------------------------
# 6. LOAN STATUS ANALYSIS
# -------------------------
df['Loan_Status'].value_counts()

plt.figure(figsize=(6,6))
df['Loan_Status'].value_counts().plot(kind='pie', autopct='%1.1f%%')
plt.title("Loan Approval vs Rejection")
plt.ylabel("")
plt.show()

# -------------------------
# 7. CREDIT SCORE VS DEFAULT
# -------------------------
credit_default = (
    df.groupby("Credit_Score")["Default_Flag"]
      .value_counts()
      .unstack()
      .fillna(0)
)
print(credit_default)

credit_default[["Yes"]].plot(kind="bar")
plt.title("Defaults by Credit Score")
plt.xlabel("Credit Score")
plt.ylabel("Number of Defaults")
plt.show()

# -------------------------
# 8. EMPLOYMENT TYPE VS DEFAULT
# -------------------------
emp_default = (
    df.groupby("Employment_Type")["Default_Flag"]
      .value_counts()
      .unstack()
      .fillna(0)
)
print(emp_default)

emp_default[["Yes"]].plot(kind="bar")
plt.title("Defaults by Employment Type")
plt.xlabel("Employment Type")
plt.ylabel("Number of Defaults")
plt.show()

# -------------------------
# 9. PROPERTY AREA VS DEFAULT
# -------------------------
area_default = (
    df.groupby("Property_Area")["Default_Flag"]
      .value_counts()
      .unstack()
      .fillna(0)
)
print(area_default)

area_default[["Yes"]].plot(kind="bar")
plt.title("Defaults by Property Area")
plt.xlabel("Property Area")
plt.ylabel("Number of Defaults")
plt.show()

# -------------------------
# 10. INCOME VS LOAN AMOUNT
# -------------------------
df[['Annual_Income', 'Loan_Amount']].corr()  # check correlation

plt.scatter(df['Annual_Income'], df['Loan_Amount'])
plt.title("Income vs Loan Amount")
plt.xlabel("Annual Income")
plt.ylabel("Loan Amount")
plt.show()
