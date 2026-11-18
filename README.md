# Experiment No. 1: Data Cleaning and Preprocessing

## Aim

To perform data cleaning and preprocessing on a business dataset using Python libraries for better data quality and analysis readiness.

## Dataset

The dataset used for this experiment is `heartdisease.csv`. It contains
medical and demographic information related to heart disease patients.

The dataset is opened and analyzed using Jupyter Notebook to study its
data structure, identify data types, and perform basic statistical
analysis for data-cleaning and preprocessing purposes.

## Algorithm

1.  Import essential Python libraries.
2.  Load the dataset using Pandas.
3.  View the dataset structure, data types, and memory usage.
4.  Check for missing values and duplicates.
5.  Perform data summary statistics using `describe()`.
6.  View initial and final records using `head()` and `tail()`.
7.  Sort and group the data based on key attributes.
8.  Rename columns or modify data where necessary.
9.  Save the cleaned dataset for further analysis.

## Functions and Methods Used in the Experiment

### 1. Data Loading and Basic Exploration

  Function / Method      Description  
  ---------------------- ------------------------------------------------------\
  `pd.read_csv()`        Reads a CSV file into a Pandas DataFrame.\
  `df.info()`            Displays column names, data types, and memory usage.\
  `df.dtypes`            Returns the data types of all columns.\
  `df['column'].dtype`   Returns the data type of a specific column.\
  `df.describe()`        Provides summary statistics for numerical columns.\
  `df.head()`            Displays the first 5 rows of the DataFrame.\
  `df.tail()`            Displays the last 5 rows of the DataFrame.\

### 2. Sorting and Grouping

  Function / Method    Description  
  -------------------- ---------------------------------------------  
  `df.sort_values()`   Sorts the DataFrame by one or more columns.  
  `df.groupby()`       Groups data based on one or more columns.  
  `groupby.sum()`      Returns the sum for each group.  
  `groupby.mean()`     Returns the mean for each group.  
  `groupby.median()`   Returns the median for each group.  
  `groupby.max()`      Returns the maximum value in each group.  
  `groupby.min()`      Returns the minimum value in each group.  

### 3. Data Summary and Manipulation  

  Function / Method   Description  
  ------------------- ----------------------------------------------  
  `df.mean()`         Calculates the mean for all numeric columns.  
  `df.rename()`       Renames columns in the DataFrame.  

### 4. Optional Additions  

  Function / Method         Description  
  ------------------------- ----------------------------------------------  
  `df.isnull().sum()`       Checks for missing values in each column.  
  `df.duplicated().sum()`   Counts duplicate rows.  
  `df.dropna()`             Removes rows containing missing values.  
  `df.fillna()`             Fills missing values with a specified value.  
  `df.drop_duplicates()`    Removes duplicate rows.  
  `df.shape`                Returns the number of rows and columns.  
  `df.columns`              Lists column names in the DataFrame.  

## Program & Output
# Import Essential Python Libraries  
import pandas as pd  
import numpy as np  
import matplotlib.pyplot as plt  
import seaborn as sns  

# Load the Dataset  
file_path = 'heartdisease.csv'  
df = pd.read_csv(file_path)  

print("--- 1. Initial Dataset Loaded Successfully ---")  
print(f"Dataset Shape (Rows, Columns): {df.shape}\n")  
  
# View Dataset Structure, Data Types, and Memory Usage  
print("--- 2. Dataset Information (`df.info()`) ---")  
print(df.info())  
print("\nColumn Data Types (`df.dtypes`):")  
print(df.dtypes)
print(f"\nList of Columns (`df.columns`): {list(df.columns)}")  

# Check for Missing Values and Duplicates  
print("\n--- 3. Checking for Missing Values and Duplicates ---")  
missing_values = df.isnull().sum()  
print("Missing Values per Column:\n", missing_values[missing_values > 0] if missing_values.sum() > 0 else "No missing values found.")  

duplicate_count = df.duplicated().sum()  
print(f"Number of Duplicate Rows: {duplicate_count}")  

# Handle Missing Values and Duplicates (Data Cleaning)  
if duplicate_count > 0:  
    df = df.drop_duplicates()  
    print("Duplicate rows removed.")  

# View Initial and Final Records  
print("\n--- 4. Initial and Final Records ---")  
print("First 5 Rows (`df.head()`):")  
print(df.head())  

print("\nLast 5 Rows (`df.tail()`):")  
print(df.tail())  

# Perform Data Summary Statistics  
print("\n--- 5. Statistical Summary (`df.describe()`) ---")  
print(df.describe())  

print("\nMean of Numeric Columns (`df.mean()`):")  
print(df.mean(numeric_only=True))  

# Sort and Group Data Based on Key Attributes  
print("\n--- 6. Sorting and Grouping Examples ---")  

# Save the Cleaned Dataset for Further Analysis  
cleaned_file_path = 'cleaned_heartdisease.csv'  
df.to_csv(cleaned_file_path, index=False)  
print(f"\n--- 7. Cleaned dataset successfully saved to '{cleaned_file_path}' ---")  

<img width="1398" height="791" alt="image" src="https://github.com/user-attachments/assets/dbbf3467-4933-4dd4-93c9-444d82dd0ff3" />



## Result

Thus to perform data cleaning and preprocessing on a business dataset using Python libraries for better data quality and analysis readiness has been executed succesfully.
