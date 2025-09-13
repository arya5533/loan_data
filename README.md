import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Step 1: Data load
df = pd.read_csv("loan_data.csv")

# Step 2: Loan Amount Distribution
sns.histplot(df["loan_amnt"], bins=30, kde=True)
plt.title("Loan Amount Distribution")
plt.show()

# Step 3: Loan Status Count
sns.countplot(x="loan_status", data=df)
plt.title("Loan Status Count")
plt.show()

# Step 4: Loan Status by Gender
sns.countplot(x="person_gender", hue="loan_status", data=df)
plt.title("Loan Status by Gender")
plt.show()

# Step 5: Income vs Loan Amount
sns.scatterplot(x="person_income", y="loan_amnt", hue="loan_status", data=df)
plt.title("Income vs Loan Amount")
plt.show()

# Step 6: Credit Score vs Loan Status
sns.boxplot(x="loan_status", y="credit_score", data=df)
plt.title("Credit Score vs Loan Status")
plt.show()
