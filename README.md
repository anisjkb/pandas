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
