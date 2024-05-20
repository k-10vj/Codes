import pandas as pd

# Read the CSV file into a pandas DataFrame
df = pd.read_csv(r'C:\Users\HP\Downloads\sales_by_customer.csv')

# Display the top 10 customer names
print("Top 10 Customer Names:")
print(df.head(10))

# Display the bottom 10 customer names
print("\nBottom 10 Customer Names:")
print(df.tail(10))

# Sort the DataFrame by sales in descending order and display the top 10 sales
top_10_sales = df.sort_values(by='sales', ascending=False).head(10)
print("\nTop 10 Sales:")
print(top_10_sales)

# Sort the DataFrame by sales in ascending order and display the least 10 sales
least_10_sales = df.sort_values(by='sales').head(10)
print("\nLeast 10 Sales:")
print(least_10_sales)

# Verify the column names in your DataFrame
print("\nColumn Names:")
print(df.columns)

# Filter rows with phone numbers (if the column name is different)
if 'mobile_phone' in df.columns:
    with_phone_number = df[df['mobile_phone'].notnull()]
    print("\nRows with Phone Numbers:")
    print(with_phone_number)
else:
    print("\nNo column named 'mobile_phone' found.")

# Filter rows without phone numbers (if the column name is different)
if 'mobile_phone' in df.columns:
    without_phone_number = df[df['mobile_phone'].isnull()]
    print("\nRows without Phone Numbers:")
    print(without_phone_number)
else:
    print("\nNo column named 'mobile_phone' found.")
