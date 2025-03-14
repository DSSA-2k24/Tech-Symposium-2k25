# **What is Pandas?**
- Pandas is a Python library used for working with data sets.
- It has functions for analyzing, cleaning, exploring, and manipulating data.

---

# **Why Use Pandas?**
- Pandas allows us to analyze big data and make conclusions based on statistical theories.
- Pandas can clean messy data sets, and make them readable and relevant.
- Relevant data is very important in data science.

---

# **Let's code**

## 1. Reading a Dataset
### **Concept: `pd.read_csv()`**
**Why it is used?**
- Reads a CSV file and converts it into a Pandas DataFrame.

**Syntax:**
```python
import pandas as pd
df = pd.read_csv('filename.csv')
```

**Example:**
```python
df = pd.read_csv('weather_data.csv')
```

## 2. Viewing Data
### **Concept: `.head()` and `.tail()`**
**Why it is used?**
- `.head(n)`: Displays the first `n` rows of the DataFrame.
- `.tail(n)`: Displays the last `n` rows of the DataFrame.

**Syntax:**
```python
df.head(n)
df.tail(n)
```

**Example:**
```python
df.head(4)
df.tail(2)
```

## 3. Statistical Summary of Data
### **Concept: `.describe()`**
**Why it is used?**
- Generates summary statistics for numerical columns.

**Syntax:**
```python
df.describe()
```

**Example:**
```python
df.describe()
```

## 4. Checking Data Structure
### **Concept: `.shape` and `.dtypes`**
**Why it is used?**
- `.shape`: Returns the number of rows and columns.
- `.dtypes`: Displays data types of columns.

**Syntax:**
```python
df.shape
df.dtypes
```

**Example:**
```python
print(df.shape)
print(df.dtypes)
```

## 5. Checking Missing/null Values
### **Concept: `.isnull().sum()`**
**Why it is used?**
- Calculate sum missing values in each column.

**Syntax:**
```python
df.isnull().sum()
```

**Example:**
```python
df.isnull().sum()
```

## 6. Sorting Data
### **Concept: `.sort_values()`**
**Why it is used?**
- Sorts the DataFrame based on a column.

**Syntax:**
```python
df.sort_values(by='column_name')
```

**Example:**
```python
df.sort_values(by='age')
```

## 7. Counting Unique Values
### **Concept: `.value_counts()` and `.nunique()`**
**Why it is used?**
- `.value_counts()`: Counts unique values in a column.
- `.nunique()`: Returns the number of unique values per column.

**Syntax:**
```python
df['column_name'].value_counts()
df.nunique()
```

**Example:**
```python
df['colours'].value_counts()
df.nunique()
```

## 8. Detecting Duplicates
### **Concept: `.duplicated().sum()`**
**Why it is used?**
- Checks for duplicate rows in the dataset.

**Syntax:**
```python
df.duplicated().sum()
```

**Example:**
```python
df.duplicated().sum()
```

## 9. Handling Duplicates
### **Concept: `.duplicated()` and `.drop_duplicates()`**
**Why it is used?**
- Identifies and removes duplicate rows.
- inplace=True makes changes in existing dataset.

**Syntax:**
```python
df.duplicated().sum()
df.drop_duplicates(inplace=True)
```

**Example:**
```python
df.duplicated().sum()
df.drop_duplicates(inplace=True)
```

## 10. Grouping Data
### **Concept: `.groupby()`**
**Why it is used?**
- Groups data based on column values and applies aggregate functions.

**Syntax:**
```python
df.groupby('column_name')['target_column'].mean()
```

**Example:**
```python
df.groupby('colour')['counts'].mean()
```

**Syntax:**
```python
df.groupby('column_name')['target_column'].sum()
```

**Example:**
```python
df.groupby('Department')['marks'].sum()
```

**Syntax:**
```python
df.groupby('column_name')['target_column'].count()
```

**Example:**
```python
df.groupby('political_party')['state'].value_counts()
```

## 11. Exporting Data
### **Concept: `.to_json()`**
**Why it is used?**
- Converts selected columns into a JSON file.

**Syntax:**
```python
df[['col1', 'col2']].to_json('output.json')
```

**Example:**
```python
data = df[['student','roll','marks','status']]
data.to_json('Student.json')
```

**Example:**
```python
df[df['marks']>90].to_json('Excellent Student.json')
```


## 12. Filtering Data
### **Concept: `df[df['column'].str.contains()]`**
**Why it is used?**
- Filters rows where a column contains a specific substring.

**Syntax:**
```python
df[df['column'].str.contains('value')]
```

**Example:**
```python
df[df['Nation'].str.contains('Ind')]
```

## 13. Conditional Filtering
### **Concept: Boolean Masking**
**Why it is used?**
- Filters rows based on multiple conditions.
- can use any comparison operator <,>,<=,>=,!=,==
- can use any logical operator & (and) , | (or)

**Syntax:**
```python
df[(df['column1'] > value) & (df['column2'] == 'value')]
```

**Example:**
```python
df[(df['name']=='John Wick') & (df['marks']==90)]
```

**Syntax:**
```python
df[df['column'] == 'value']
```

**Example:**
```python
df[(df['Gender']=='Male') & (df['Class']=='AI&DS') & (df['Marks']>35)]
```

**Syntax:**
```python
df[(df['column1'] > value) & (df['column2'] == 'value')]
```

**Example:**
```python
df[(df['votes']>20) & (df['state']=='Goa')]
```

## 14. Replacing Values
### **Concept: `.str.replace()`**
**Why it is used?**
- Replaces occurrences of a string within a column.

**Syntax:**
```python
df['column_name'] = df['column_name'].str.replace('old', 'new')
```

**Example:**
```python
df['Class'] = df['Class'].str.replace('Artificial Intelligence','AI')
```

## 15. Checking Data Information
### **Concept: `.info()`**
**Why it is used?**
- Provides metadata about the DataFrame including column names, data types, and non-null counts.

**Syntax:**
```python
df.info()
```

**Example:**
```python
df.info()
```

## 16. Calculating Averages
### **Concept: `.mean()`**
**Why it is used?**
- Computes the mean of a column.

**Syntax:**
```python
df['column_name'].mean()
```

**Example:**
```python
df['age'].mean()
```

**Example: Mean/ Average marks of AI&DS class.**
```python
df[df['Class']=='AI&DS']['marks'].mean()
```

## 17. Finding Maximum Value in Filtered Data
### **Concept: `.max()`**
**Why it is used?**
- Retrieves the maximum value from a column.

**Syntax:**
```python
df['column_name'].max()
```

**Example:**
```python
df['age'].max()
```

**Example: Maximum vote given in Goa state to BJP party.**
```python
df[(df['State']=='Goa') & (df['Party']=='BJP')]['vote'].max()
```

## 18. Finding Correlation
### **Concept: `.corr()`**
**Why it is used?**
- Computes pairwise correlation between numerical columns.

**Syntax:**
```python
df.corr()
```

**Example:**
```python
df.corr(numeric_only=True)
```

## 20. Counting Values with Multiple Conditions
### **Concept: `.groupby()` with `.size()`**
**Why it is used?**
- Counts the number of occurrences for each group.

**Syntax:**
```python
df[df['column'] > value].groupby(['col1', 'col2']).size()
```

**Example:**
```python
df[df['age'] > 19].groupby(['gender', 'class']).size()
```

## 21. Finding Correlation Between Two Columns
### **Concept: `.corr()`**
**Why it is used?**
- Measures the correlation between two columns.

**Syntax:**
```python
df['col1'].corr(df['col2'])
```

**Example:**
```python
df['cgpa'].corr(df['placement'])
```


## 22. Viewing Column Names
### **Concept: `.columns`**
**Why it is used?**
- Returns a list of all column names.

**Syntax:**
```python
df.columns
```

**Example:**
```python
print(df.columns)
```



## 23. Dropping Columns
### **Concept: `.drop()`**
**Why it is used?**
- Removes specified columns from the dataset.

**Syntax:**
```python
df.drop(columns=['column_name'], inplace=True)
```

**Example:**
```python
df.drop(columns=['Student ID'], inplace=True)
```

## 24. Random Sampling
### **Concept: `.sample()`**
**Why it is used?**
- Retrieves random samples from the dataset.

**Syntax:**
```python
df.sample(n)
```

**Example:Random 4 rows from dataset**
```python
df.sample(4)
```


## 25. Calculating Mean
### **Concept: `.mean()`**
**Why it is used?**
- Computes the average value of a column.

**Syntax:**
```python
df['column_name'].mean()
```

**Example: mean of price range of Books which title contains "Engineering"**
```python
df[(df['Text'].str.contains('engineering'))]['Price range'].mean()
```

## 26. Summing Values
### **Concept: `.sum()`**
**Why it is used?**
- Returns the total sum of values in a column.

**Syntax:**
```python
df['column_name'].sum()
```

**Example:**
```python
df[(df['Class'] == 'AI&DS') & (df['Roll Number'] == 90)]['fees'].sum()
```

## 27. Mapping Values
### **Concept: `.map()`**
**Why it is used?**
- Replaces values in a column using a dictionary.

**Syntax:**
```python
df['column_name'] = df['column_name'].map({'old_value': 'new_value'})
```

**Example:**
```python
df['Fruits'] = df['Fruits'].map({'Orange': 'O', 'Mango': 'M'})
```

## 28. String Filtering
### **Concept: `.str.contains()`**
**Why it is used?**
- Filters rows where a column contains a specific substring.

**Syntax:**
```python
df[df['column_name'].str.contains('substring', na=False)]
```

**Example:**
```python
df[df['Country'].str.contains('Ind', na=False)]
```

## 29. Finding Most Frequent Value
### **Concept: `.value_counts().idxmax()`**
**Why it is used?**
- Identifies the most frequent value in a column.

**Syntax:**
```python
df['column_name'].value_counts().idxmax()
```

**Example:return name of branch which occurred maximum number of times in the dataset.**
```python
df['branch'].value_counts().idxmax()
```

## 30. Converting Date Column
### **Concept: `pd.to_datetime()`**
**Why it is used?**
- Converts a column containing date strings into a DateTime format.

**Syntax:**
```python
df['new_column'] = pd.to_datetime(df['date_column'])
```

**Example:**
```python
df['Birth Date'] = pd.to_datetime(df['Birth Date'])
```


## 31. Filtering Data and Exporting JSON
### **Concept: `Filtering with Conditions` & `.to_json()`**
**Why it is used?**
- Filters data based on specified conditions and exports the result to a JSON file.

**Syntax:**
```python
df[df['column'] > value].to_json('filename.json')
```

**Example:All students in 2016 who have marks more than 80.**
```python
Awards = df[(df['year']==2016)&(df['marks']>80)]['student']
Awards.to_json('Award 2016.json')
```

Here’s the generalized version of the new concepts, making them more like Pandas documentation:  

---

## 32. Finding the Maximum Value in Grouped Data  
### **Concept: `.groupby()` and `.idxmax()`**  
**Why it is used?**  
- Groups data based on a categorical column and finds the index of the maximum value for a numerical column.  

**Syntax:**  
```python
df.groupby('grouping_column')['numerical_column'].mean().idxmax()
```  

**Example:**  
```python
df.groupby('Class')['Marks'].mean().idxmax()
```  

---

## 33. Summing Values Based on a Condition  
### **Concept: `.sum()`**  
**Why it is used?**  
- Computes the total sum of a numerical column that meets specific conditions.  

**Syntax:**  
```python
df[df['condition_column'] == value]['numerical_column'].sum()
```  

**Example:**  
```python
df[df['Admission year'] == 2017]['marks'].sum()
```  

---

## 34. Filtering Rows Based on a Condition  
### **Concept: `Filtering Conditions`**  
**Why it is used?**  
- Selects rows from the DataFrame based on a specified condition.  

**Syntax:**  
```python
df[df['numerical_column'] > threshold]
```  

**Example:**  
```python
df[df['marks'] > 10]
```  

---

## 35. Creating Data Visualizations  
### **Concept: `.plot.scatter()` and `.plot.hist()`**  
**Why it is used?**  
- Generates visualizations such as scatter plots and histograms to analyze trends and distributions in data.  

**Syntax:**  
```python
df.plot.scatter(x='x_column', y='y_column', alpha=0.5, color='color', figsize=(width, height))  
df['numerical_column'].plot(kind='hist', bins=number_of_bins, color='color', edgecolor='black', figsize=(width, height))  
```  

**Example:**  
```python
df.plot.scatter(x='cgpa', y='package in rupees', alpha=0.5, color='red', figsize=(8,6))    
```  

```py
df['Age'].plot(kind='hist', bins=30, color='green', edgecolor='black', figsize=(10,5))
```

---
