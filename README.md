📊 Data Binning and Data Formatting in Python
📌 Overview
This project demonstrates how to perform data binning and data formatting using Python. These are essential preprocessing techniques used in data analysis, machine learning, and data visualization.

Data Binning: Grouping continuous values into discrete intervals (bins).
Data Formatting: Cleaning and transforming data into a consistent and usable format.
⚙️ Requirements
Make sure you have the following installed:

pip install pandas numpy
📊 Data Binning
🔹 What is Data Binning?
Data binning (also called bucketing) is used to convert continuous data into categorical data.

🔹 Example
import pandas as pd

# Sample data
data = {'Age': [18, 22, 25, 30, 35, 40, 45, 50]}
df = pd.DataFrame(data)

# Define bins and labels
bins = [0, 20, 30, 40, 60]
labels = ['Teen', 'Young Adult', 'Adult', 'Senior']

# Apply binning
df['Age Group'] = pd.cut(df['Age'], bins=bins, labels=labels)

print(df)
🔹 Output
   Age     Age Group
0   18          Teen
1   22   Young Adult
2   25   Young Adult
3   30   Young Adult
4   35         Adult
5   40         Adult
6   45        Senior
7   50        Senior
🧹 Data Formatting
🔹 What is Data Formatting?
Data formatting ensures that data is consistent, clean, and ready for analysis.

🔹 Common Tasks
Handling missing values
Changing data types
Formatting strings
Normalizing values
🔹 Example
import pandas as pd

# Sample data
data = {
    'Name': ['Alice ', ' Bob', 'Charlie'],
    'Salary': ['50000', '60000', '70000']
}

df = pd.DataFrame(data)

# Remove extra spaces
df['Name'] = df['Name'].str.strip()

# Convert Salary to integer
df['Salary'] = df['Salary'].astype(int)

print(df)
🔹 Output
      Name  Salary
0    Alice   50000
1      Bob   60000
2  Charlie   70000
🔄 Combining Binning & Formatting
import pandas as pd

df = pd.read_csv('data/sample_data.csv')

# Clean column names
df.columns = df.columns.str.strip()

# Convert columns
df['Age'] = df['Age'].astype(int)

# Apply binning
bins = [0, 18, 35, 60, 100]
labels = ['Minor', 'Youth', 'Middle Age', 'Senior']
df['Age Group'] = pd.cut(df['Age'], bins=bins, labels=labels)

print(df.head())
🚀 Use Cases
Customer segmentation
Data preprocessing for ML models
Reporting and dashboards
Data visualization grouping
🧠 Tips
Use pd.cut() for fixed bins
Use pd.qcut() for quantile-based bins
Always clean data before binning
Validate results after transformations
📚 References
Pandas Documentation: https://pandas.pydata.org/docs/
NumPy Documentation: https://numpy.org/doc/
