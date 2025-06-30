## 🧠 Pandas & Visualization Cheat Sheet – Real-World Examples

| Function / Method | Real-World Example |
|-------------------|--------------------|
| `reset_index()` | After grouping bank accounts by gender and calculating totals, reset index to flatten the DataFrame. |
| `loc[]` | Select all female customers from Dhaka branch for targeted marketing. |
| `info()` | Quickly check data types and null counts in a customer demographics dataset. |
| `drop()` | Remove the 'Unnamed: 0' column after importing a CSV with redundant indexing. |
| `str.strip().str.replace()` | Clean up inconsistent spacing in customer names before merging datasets. |
| `duplicated()` | Identify duplicate account entries due to system migration. |
| `drop_duplicates(inplace=True)` | Remove repeated transaction logs to ensure accurate monthly summaries. |
| `round()` | Round average transaction amounts to 2 decimal places for dashboard display. |
| `to_datetime()` | Convert 'account_open_date' from string to datetime for tenure analysis. |
| `groupby()` | Group accounts by region and gender to analyze inclusion trends. |
| `std()` | Measure variability in monthly deposits across branches. |
| `var()` | Assess variance in loan amounts to understand risk distribution. |
| `mean()` | Calculate average balance per customer segment. |
| `agg()` | Aggregate multiple metrics (mean, sum, count) for each branch in one go. |
| `head()` | Preview the first 5 rows of a cleaned dataset before visualization. |
| `columns` | Rename columns like 'acc_no' to 'Account Number' for clarity in reports. |
| `nunique()` | Count unique account types offered across branches. |
| `describe()` | Get summary stats of customer ages to tailor financial products. |
| `astype()` | Convert 'gender' to category dtype to optimize memory usage. |
| `dtype` | Check if 'balance' is float before performing arithmetic operations. |
| `value_counts()` | Count how many customers fall into each income bracket. |
| `plot(kind='bar')` | Visualize number of accounts by product type in a bar chart. |
| `type()` | Confirm if a variable is a DataFrame before applying transformations. |
| `plt.figure(figsize=(10,6))` | Set figure size for a clean, readable bar chart in a dashboard. |
| `plt.title(), plt.xlabel(), plt.ylabel()` | Add context to a plot showing gender-wise account distribution. |
| `sort_values(ascending=False)` | Rank branches by total deposits in descending order. |
| `dt.month` | Extract month from transaction dates to analyze seasonal trends. |
| `shape` | Check dataset size before merging or filtering. |
| `index` | Set 'Customer ID' as index for easier lookup and slicing. |
| `dtypes` | Review data types to ensure compatibility before exporting to Excel. |
| `count()` | Count non-null entries in 'email' column to assess data completeness. |
| `isnull()` | Identify missing values in 'phone_number' for data cleaning. |
| `dropna()` | Remove rows with missing 'branch_code' before aggregation. |
| `isin()` | Filter transactions from specific high-value branches. |
| `str.contains()` | Find customers whose occupation includes 'Engineer'. |
| `str.split()` | Split 'full_name' into 'first_name' and 'last_name' for personalization. |
| `dt.year.value_counts()` | Count number of accounts opened each year to track growth. |
| `sns.countplot(df['Col_name'])` | Plot count of customers by education level using Seaborn. |
| `max(), min()` | Find highest and lowest transaction amounts in a given month. |

---

### 🧠 1–10: Data Cleaning & Exploration Essentials

| Function | Real-World Example |
|---------|--------------------|
| **`reset_index()`** | After filtering a DataFrame of bank transactions by region, the index becomes disjointed. Use `reset_index()` to tidy it up before exporting to Excel. |
| **`loc[]`** | You want to retrieve all rows where `Gender == 'Female'` in a customer dataset: `df.loc[df['Gender'] == 'Female']`. |
| **`info()`** | You’ve loaded a CSV of account holders. Use `df.info()` to quickly check for nulls, data types, and memory usage before analysis. |
| **`drop()`** | You want to remove the `Customer_ID` column before clustering analysis: `df.drop('Customer_ID', axis=1)`. |
| **`str.strip().str.replace(r'\s+', ' ', regex=True)`** | A column `Branch_Name` has inconsistent spacing like `"  Dhaka   Central  "`. Clean it with: `df['Branch_Name'] = df['Branch_Name'].str.strip().str.replace(r'\s+', ' ', regex=True)` |
| **`duplicated()`** | In a dataset of loan applications, check for duplicate entries: `df[df.duplicated()]`. |
| **`drop_duplicates(inplace=True)`** | After identifying duplicates, remove them permanently: `df.drop_duplicates(inplace=True)`. |
| **`round()`** | Round off interest rates to 2 decimal places: `df['Interest_Rate'] = df['Interest_Rate'].round(2)`. |
| **`to_datetime()`** | Convert a `Date_of_Transaction` column from string to datetime: `df['Date_of_Transaction'] = pd.to_datetime(df['Date_of_Transaction'])`. |
| **`groupby()`** | Group customer accounts by `Gender` and calculate average balance: `df.groupby('Gender')['Balance'].mean()` |

---

### 🧠 11–20: Statistical Summaries & Grouping

| Function | Real-World Example | Input | Output |
|---------|--------------------|--------|--------|
| **`std()`** | In a bank’s credit score dataset, calculate the **standard deviation** of customer ages to understand age variability. | `df['Age'].std()` | `12.45` |
| **`var()`** | For a loan portfolio, check the **variance** in loan amounts to assess risk spread. | `df['Loan_Amount'].var()` | `1.6e+06` |
| **`mean()`** | Calculate the **average balance** of savings accounts by region. | `df['Balance'].mean()` | `₹45,320.67` |
| **`agg()`** | Group by `Gender` and get both **mean and max** of `Balance`. | `df.groupby('Gender')['Balance'].agg(['mean', 'max'])` | Table with mean & max per gender |
| **`head()`** | Preview the **first 5 rows** of a customer dataset. | `df.head()` | First 5 rows of the DataFrame |
| **`columns`** | List all **column names** in a dataset. | `df.columns` | `Index(['Name', 'Age', 'Balance', ...])` |
| **`unique()`** | Find all **unique account types** in a column. | `df['Account_Type'].unique()` | `['Savings', 'Current', 'Fixed']` |
| **`nunique()`** | Count how many **unique cities** customers are from. | `df['City'].nunique()` | `27` |
| **`describe()`** | Get a **summary** of numerical columns like `Balance`, `Age`, etc. | `df.describe()` | Count, mean, std, min, max, etc. |
| **`astype()`** | Convert `Age` from float to integer for reporting. | `df['Age'] = df['Age'].astype(int)` | `Age` column now has `int` dtype |

---

**11–20: Statistical Summaries & Grouping**

| Function | Real-World Example |
|----------|--------------------|
| std() | In a credit risk model, calculate the standard deviation of customer income to assess variability in earning potential: `df['Income'].std()` |
| var() | In a portfolio analysis, check the variance of investment returns to understand risk: `df['Returns'].var()` |
| mean() | Calculate the average monthly transaction amount for savings accounts: `df['Monthly_Transaction'].mean()` |
| agg() | Group by `Branch` and calculate both total and average deposits: `df.groupby('Branch')['Deposit'].agg(['sum', 'mean'])` |
| head() | Preview the first 5 rows of a new customer dataset to verify structure: `df.head()` |
| columns | List all column names in a dataset before renaming or reordering: `df.columns` |
| unique() | Identify all unique account types in a dataset: `df['Account_Type'].unique()` |
| nunique() | Count how many unique cities customers are from: `df['City'].nunique()` |
| describe() | Get a quick statistical summary of numerical columns like `Balance`, `Age`, etc.: `df.describe()` |
| astype() | Convert `Age` from float to integer for reporting: `df['Age'] = df['Age'].astype(int)` |

---

### 🧠 21–30: Data Profiling & Visualization

| Function | Real-World Example | Input | Output | Output Example |
|---------|--------------------|--------|--------|----------------|
| **`dtype`** | Check the data type of a column like `Age` to ensure it's numeric before analysis. | `df['Age'].dtype` | `dtype('int64')` | `int64` |
| **`value_counts()`** | Count how many customers fall into each `Account_Type`. | `df['Account_Type'].value_counts()` | Series with counts | `Savings: 1200, Current: 800` |
| **`plot(kind='bar')`** | Visualize number of accounts by type. | `df['Account_Type'].value_counts().plot(kind='bar')` | Bar chart | ![Bar Chart](https://www.geeksforgeeks.org/wp-content/uploads/bar-plot-in-matplotlib.png) |
| **`type()`** | Check if a variable is a DataFrame or Series. | `type(df['Balance'])` | `<class 'pandas.core.series.Series'>` | Series |
| **`plt.figure(figsize=(10,6))`** | Resize a plot for better readability in a dashboard. | `plt.figure(figsize=(10,6))` | Enlarged plot | Wider, clearer chart |
| **`plt.title(), plt.xlabel(), plt.ylabel()`** | Add context to a bar chart showing account distribution. | `plt.title('Account Types')` | Labeled chart | Title and axis labels |
| **`sort_values(ascending=False)`** | Sort branches by total deposits in descending order. | `df.sort_values('Total_Deposit', ascending=False)` | Sorted DataFrame | Top branch first |
| **`dt.month`** | Extract month from `Transaction_Date` for monthly trend analysis. | `df['Month'] = df['Transaction_Date'].dt.month` | New column `Month` | `1, 2, 3...` |
| **`shape`** | Get the number of rows and columns in your dataset. | `df.shape` | Tuple | `(10000, 12)` |
| **`index`** | View or reset the index of a DataFrame. | `df.index` | RangeIndex or custom | `RangeIndex(start=0, stop=10000, step=1)` |

---

Single table summarizing. This should give you a clear, contextual reference for your BI portfolio and storytelling:

| Function / Method                          | Real-World Example                                                                                   |
|-------------------------------------------|--------------------------------------------------------------------------------------------------------|
| `reset_index()`                            | After grouping bank accounts by gender and calculating totals, reset index to flatten the DataFrame. |
| `loc[]`                                    | Select all female customers from Dhaka branch for targeted marketing.                                 |
| `info()`                                   | Quickly check data types and null counts in a customer demographics dataset.                          |
| `drop()`                                   | Remove the 'Unnamed: 0' column after importing a CSV with redundant indexing.                         |
| `str.strip().str.replace()`                | Clean up inconsistent spacing in customer names before merging datasets.                              |
| `duplicated()`                             | Identify duplicate account entries due to system migration.                                           |
| `drop_duplicates(inplace=True)`           | Remove repeated transaction logs to ensure accurate monthly summaries.                                |
| `round()`                                  | Round average transaction amounts to 2 decimal places for dashboard display.                          |
| `to_datetime()`                            | Convert 'account_open_date' from string to datetime for tenure analysis.                              |
| `groupby()`                                | Group accounts by region and gender to analyze inclusion trends.                                      |
| `std()`                                    | Measure variability in monthly deposits across branches.                                              |
| `var()`                                    | Assess variance in loan amounts to understand risk distribution.                                      |
| `mean()`                                   | Calculate average balance per customer segment.                                                       |
| `agg()`                                    | Aggregate multiple metrics (mean, sum, count) for each branch in one go.                              |
| `head()`                                   | Preview the first 5 rows of a cleaned dataset before visualization.                                   |
| `columns`                                  | Rename columns like 'acc_no' to 'Account Number' for clarity in reports.                              |
| `nunique()`                                | Count unique account types offered across branches.                                                   |
| `describe()`                               | Get summary stats of customer ages to tailor financial products.                                      |
| `astype()`                                 | Convert 'gender' to category dtype to optimize memory usage.                                          |
| `dtype`                                    | Check if 'balance' is float before performing arithmetic operations.                                  |
| `value_counts()`                           | Count how many customers fall into each income bracket.                                               |
| `plot(kind='bar')`                         | Visualize number of accounts by product type in a bar chart.                                          |
| `type()`                                   | Confirm if a variable is a DataFrame before applying transformations.                                 |
| `plt.figure(figsize=(10,6))`               | Set figure size for a clean, readable bar chart in a dashboard.                                       |
| `plt.title(), plt.xlabel(), plt.ylabel()`  | Add context to a plot showing gender-wise account distribution.                                       |
| `sort_values(ascending=False)`             | Rank branches by total deposits in descending order.                                                  |
| `dt.month`                                 | Extract month from transaction dates to analyze seasonal trends.                                      |
| `shape`                                    | Check dataset size before merging or filtering.                                                       |
| `index`                                    | Set 'Customer ID' as index for easier lookup and slicing.                                             |
| `dtypes`                                   | Review data types to ensure compatibility before exporting to Excel.                                  |
| `count()`                                  | Count non-null entries in 'email' column to assess data completeness.                                 |
| `isnull()`                                 | Identify missing values in 'phone_number' for data cleaning.                                          |
| `dropna()`                                 | Remove rows with missing 'branch_code' before aggregation.                                            |
| `isin()`                                   | Filter transactions from specific high-value branches.                                                |
| `str.contains()`                           | Find customers whose occupation includes 'Engineer'.                                                  |
| `str.split()`                              | Split 'full_name' into 'first_name' and 'last_name' for personalization.                              |
| `dt.year.value_counts()`                   | Count number of accounts opened each year to track growth.                                            |
| `sns.countplot(df['Col_name'])`            | Plot count of customers by education level using Seaborn.                                             |
| `max(), min()`                             | Find highest and lowest transaction amounts in a given month.                                         |
