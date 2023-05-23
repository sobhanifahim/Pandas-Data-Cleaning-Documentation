# Pandas Data Cleaning Documentation</h1>

## 1. Introduction to Pandas ##

Pandas is a popular open-source data manipulation and analysis library for Python. It provides easy-to-use data structures and data analysis tools to work efficiently with structured data.
Key features of Pandas include:

- Data Frame objects for handling tabular data.
- Efficient data structures for handling large datasets.
- Built-in tools for data cleaning, transformation, and analysis.
- Integration with other Python libraries for data visualization and machine learning.

## 2. Installation ##

To install Pandas, you can use the following command using pip:

```pip install pandas```

Make sure you have Python and pip installed on your system before running this command.

## 3. Importing Pandas ##

To start using Pandas in your Python script / Jupyter Notebook / Google Colab, you need to import the library. Conventionally, Pandas is imported with the alias `pd`, the alias can be any name:

```import pandas as pd```

## 4. Data Structures in Pandas ##

Pandas provides two main data structures for handling data:

Series

A Series is a one-dimensional labeled array capable of holding any data type. It can be seen as a column in a spreadsheet or a single column of a Data Frame. A Series consists of two components: the data and the index.



“import pandas as pd
> Creating a Series
s = pd.Series([6, 7, 8, np.nan, 10, 11])

#Printing the Series
print(s)”

Output:

0    6.0<br>
1    7.0<br>
2    8.0<br>
3    NaN<br>
4    10.0<br>
5    11.0<br>
dtype: float64 <br>

# Data Frame

A Data Frame is a two-dimensional labeled data structure with columns of potentially different data types. It can be seen as a spreadsheet or a SQL table. A Data Frame consists of three components: the data, the index, and the column names.<br>

```import pandas as pd```

### Creating a Data Frame

```data = {'Name': ['Anas', 'Fahim', 'Najirul', 'Mubin'],<br>
        'Age': [23, 24, 29, 27],<br>
        'District': ['Joypurhat', 'Munshiganj', 'Kishoregonj', 'Tangail']}<br>
df = pd.DataFrame(data)<br>
#Printing the Data Frame<br>
print(df) ```

Output:

   Name    Age    District<br>
0 Anas     23     Joypurhat<br>
1 Fahim    24     Munshiganj<br>
2 Najirul  29     Kishoregonj<br>
3 Mubin    27     Tangail<br>

<b>5. Loading Data into Pandas</b>

Pandas provides various methods for loading data from different sources such as CSV files, Excel files, databases, and more. Here's an example of loading data from a CSV file:<br>

“import pandas as pd

#Loading data from a CSV file
df = pd.read_csv('data.csv')   //you should provide the file path if it is inside a                        
                                                 directory<br>

#Printing the DataFrame<br>
print(df)”<br>

Make sure to replace 'data.csv' with the actual path to your.<br>
<b>6. Data Cleaning Techniques</b><br>
Data cleaning is an essential step in the data analysis process. Here are some common data cleaning techniques using Pandas:<br>
Handling Missing Values<br>
Missing values are common in real-world datasets. Pandas provides several methods for handling missing values, such as dropna(),<br> fillna(), and interpolate().<br>

“import pandas as pd<br>

#Dropping rows with missing values<br>
 df.dropna()<br>
#You can use .isna() to check if there is presence of null value as NaN, it will return true or false <br>
df.isna()<br>
#To count the total number of  missing values in each column  we can use .sum() with df.isna()<br>
df.isna().sum()<br>
#Filling missing values with a specific value <br>
df.fillna(0) <br>

#Filling missing values with themean of the column <br>
df.fillna(df.mean()) <br>

#Interpolating missing values using linear interpolation <br>
df.interpolate()” <br>
 
Removing Duplicates<br>
Duplicate rows can affect the accuracy of data analysis. Pandas provides the drop_duplicates() method to remove duplicate rows from a DataFrame.<br>

“import pandas as pd <br>

#Dropping duplicate rows<br>
 df.drop_duplicates()”<br>

#To indicate the duplicate rows we can use .duplicated(subset)<br>
df.duplicated(subset)<br>
#To drop duplicate rows based on specific column we can use .duplicates(subset)<br>
df.duplicates(subset)<br>

<b>7.Handling Outliers</b><br>
Outliers are extreme values that deviate from the normal range of data. Pandas allows you to detect and handle outliers using various statistical techniques.<br>

“import pandas as pd <br>

#Detecting outliers using z-score<br> 
from scipy import stats <br>
z_scores = stats.zscore(df['column_name'])<br> 
outliers = df[(z_scores > 3) | (z_scores < -3)]<br> 

#Removing outliers <br>
df = df[(z_scores < 3) & (z_scores > -3)] ”<br>

<b>8.Data Type Conversion</b><br>
Pandas provides methods to convert data types of columns, such as astype(), to_numeric(), and to_datetime().<br>

“import pandas as pd <br>

#Converting a column to a different data type<br> 
df['column_name'] = df['column_name'].astype(int)<br> 

#Converting a column to numeric data type <br>
df['column_name'] = pd.to_numeric(df['column_name'], errors='coerce')<br>

 #Converting a column to datetime data type <br>
 df['date_column'] = pd.to_datetime(df['date_column']) ”<br>
 
<b>9.Renaming Columns</b><br>
You can rename columns in a DataFrame using the rename() method.<br>
“import pandas as pd<br>
#Renaming columns<br>
df = df.rename(columns={'old_name': 'new_name'}) ”<br>

<b>10.Handling Categorical Data</b><br>
Pandas provides methods to handle categorical data, such as get_dummies() for one-hot encoding and astype('category') for converting a column to a categorical data type.<br>


“import pandas as pd<br>
#One-hot encoding categorical columns<br>
df_encoded = pd.get_dummies(df, columns=['categorical_column'])<br>
#Converting a column to categorical data type<br>
df['column_name'] = df['column_name'].astype('category') ”<br>

<b>11.Filtering and Sorting Data</b><br>
Pandas allows you to filter and sort data based on specific criteria using Boolean indexing and sorting methods.<br>

“import pandas as pd<br>
#Filtering data based on a condition<br>
filtered_df = df[df['column_name'] > 10]<br>
#Sorting data by a column<br>
sorted_df = df.sort_values(by='column_name') ”<br>
<b>12.Conclusion</b><br>
Pandas is a powerful library for cleaning and manipulating data in Python. This document provides an introduction to Pandas, installation instructions, and covers various techniques for data cleaning with Pandas. By leveraging Pandas features, you can efficiently clean and preprocess your data, preparing it for further analysis and modeling.
## 11. Load Json file in pandas ##
'''import pandas as pd
df = pd.read_json('data.json')'''
