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
# Creating a Series
s = pd.Series([6, 7, 8, np.nan, 10, 11])

# Printing the Series
print(s)”

Output:

0    6.0
1    7.0
2    8.0
3    NaN
4    10.0
5    11.0
dtype: float64

Data Frame

A Data Frame is a two-dimensional labeled data structure with columns of potentially different data types. It can be seen as a spreadsheet or a SQL table. A Data Frame consists of three components: the data, the index, and the column names.

“import pandas as pd
# Creating a Data Frame
data = {'Name': ['Anas', 'Fahim', 'Najirul', 'Mubin'],
        'Age': [23, 24, 29, 27],
        'District': ['Joypurhat', 'Munshiganj', 'Kishoregonj', 'Tangail']}
df = pd.DataFrame(data)
# Printing the Data Frame
print(df)”

Output:

   Name   Age    District
0 Anas     23        Joypurhat
1 Fahim    24      Munshiganj
2 Najirul    29     Kishoregonj
3 Mubin     27     Tangail
