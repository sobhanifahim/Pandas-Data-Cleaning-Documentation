<h1>Pandas Data Cleaning Documentation</h1>

<b>1. Introduction to Pandas</b>

Pandas is a popular open-source data manipulation and analysis library for Python. It provides easy-to-use data structures and data analysis tools to work efficiently with structured data.
Key features of Pandas include:

- Data Frame objects for handling tabular data.
- Efficient data structures for handling large datasets.
- Built-in tools for data cleaning, transformation, and analysis.
- Integration with other Python libraries for data visualization and machine learning.

<b>2. Installation</b>

To install Pandas, you can use the following command using pip:

“pip install pandas”

Make sure you have Python and pip installed on your system before running this command.

<b>3. Importing Pandas</b>

To start using Pandas in your Python script / Jupyter Notebook / Google Colab, you need to import the library. Conventionally, Pandas is imported with the alias `pd`, the alias can be any name:

“import pandas as pd”

<b>4. Data Structures in Pandas</b>

Pandas provides two main data structures for handling data:

Series

A Series is a one-dimensional labeled array capable of holding any data type. It can be seen as a column in a spreadsheet or a single column of a Data Frame. A Series consists of two components: the data and the index.



“import pandas as pd
#Creating a Series
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

Data Frame<br>

A Data Frame is a two-dimensional labeled data structure with columns of potentially different data types. It can be seen as a spreadsheet or a SQL table. A Data Frame consists of three components: the data, the index, and the column names.<br>

“import pandas as pd<br>
#Creating a Data Frame<br>
data = {'Name': ['Anas', 'Fahim', 'Najirul', 'Mubin'],<br>
        'Age': [23, 24, 29, 27],<br>
        'District': ['Joypurhat', 'Munshiganj', 'Kishoregonj', 'Tangail']}<br>
df = pd.DataFrame(data)<br>
#Printing the Data Frame<br>
print(df)”<br>

Output:

   Name    Age    District<br>
0 Anas     23     Joypurhat<br>
1 Fahim    24     Munshiganj<br>
2 Najirul  29     Kishoregonj<br>
3 Mubin    27     Tangail<br>


5. Loading Data into Pandas

Pandas provides various methods for loading data from different sources such as CSV files, Excel files, databases, and more. Here's an example of loading data from a CSV file:

“import pandas as pd

#Loading data from a CSV file
df = pd.read_csv('data.csv')   //you should provide the file path if it is inside a                        
                                                 directory

#Printing the DataFrame
print(df)”

Make sure to replace 'data.csv' with the actual path to your.
 
6. Data Cleaning Techniques
Data cleaning is an essential step in the data analysis process. Here are some common data cleaning techniques using Pandas:
Handling Missing Values
Missing values are common in real-world datasets. Pandas provides several methods for handling missing values, such as dropna(), fillna(), and interpolate().

“import pandas as pd

#Dropping rows with missing values
 df.dropna()
#You can use .isna() to check if there is presence of null value as NaN, it will return true or false 
df.isna()
#To count the total number of  missing values in each column  we can use .sum() with df.isna()
df.isna().sum()
#Filling missing values with a specific value 
df.fillna(0) 

#Filling missing values with themean of the column 
df.fillna(df.mean()) 

#Interpolating missing values using linear interpolation 
df.interpolate()” 
 
Removing Duplicates
Duplicate rows can affect the accuracy of data analysis. Pandas provides the drop_duplicates() method to remove duplicate rows from a DataFrame.

“import pandas as pd 

# Dropping duplicate rows
 df.drop_duplicates()”

#To indicate the duplicate rows we can use .duplicated(subset)
df.duplicated(subset)
#To drop duplicate rows based on specific column we can use .duplicates(subset)
df.duplicates(subset)
