# **Numpy Notes**

## 1. Finding the Total Number of Rows
### **Concept: `np.shape()`**
**Why it is used?**
- Retrieves the number of rows (records) in a dataset.

**Syntax:**
```python
rows = np.shape(df)[0]
```

**Example:**
```python
total_rows = np.shape(df)[0]
print(total_rows)
```


## 2. Finding the Total Number of Columns
### **Concept: `np.shape()`**
**Why it is used?**
- Retrieves the number of columns in a dataset.

**Syntax:**
```python
columns = np.shape(df)[1]
```

**Example:**
```python
total_columns = np.shape(df)[1]
print(total_columns)
```


## 3. Extracting First N Values from a Column
### **Concept: Indexing NumPy Arrays**
**Why it is used?**
- Extracts a subset of values from a column for quick analysis.

**Syntax:**
```python
first_n_values = np.array(df['column_name'])[:n]
```

**Example:**
```python
first_5_countries = np.array(df['country'])[:5]
print(first_5_countries)
```


## 4. Finding the Maximum Value in a Column
### **Concept: `np.max()`**
**Why it is used?**
- Determines the highest value in a numerical column.

**Syntax:**
```python
max_value = np.max(array)
```

**Example:**
```python
max_age = np.max(np.array(df['age']))
print(max_age)
```


## 5. Counting Unique Values in a Column
### **Concept: `np.unique()`**
**Why it is used?**
- Identifies unique values and counts their occurrences.

**Syntax:**
```python
unique_values = np.unique(array).size
```

**Example:**
```python
unique_contries = np.unique(np.array(df['contries'])).size
print(unique_contries)
```


## 6. Extracting the Last N Values from a Column
### **Concept: Negative Indexing in NumPy**
**Why it is used?**
- Retrieves the last N elements from a column.

**Syntax:**
```python
last_n_values = np.array(df['column_name'])[-n:]
```

**Example:**
```python
last_5_cities = np.array(df['city'])[-5:]
print(last_5_cities)
```


## 7. Summing All Values in a Column
### **Concept: `np.sum()`**
**Why it is used?**
- Computes the total sum of a numerical column.

**Syntax:**
```python
total_sum = np.sum(array)
```

**Example:**
```python
total_marks = np.sum(np.array(df['marks']))
print(total_marks)
```


## 8. Computing Median of a Column
### **Concept: `np.median()`**
**Why it is used?**
- Determines the middle value in a sorted dataset.

**Syntax:**
```python
median_value = np.median(array)
```

**Example:**
```python
median_package = np.median(np.array(df['package']))
print(median_package)
```


## 9. Calculating Standard Deviation of a Column
### **Concept: `np.std()`**
**Why it is used?**
- Measures the dispersion of data points from the mean.

**Syntax:**
```python
std_value = np.std(array)
```

**Example:**
```python
std_cgpa = np.std(np.array(df['CGPA']))
print(std_cgpa)
```


## 10. Finding Percentage of Values Above Average
### **Concept: `np.mean()` and Boolean Masking**
**Why it is used?**
- Computes the percentage of values exceeding the average.

**Syntax:**
```python
percentage = (np.sum(array > np.mean(array)) / len(array)) * 100
```

**Example:**
```python
bike_speed = (np.sum(np.array(df['bike_speed']) > np.mean(df['bike_speed'])) / len(df)) * 100
```


## 11. Finding the Most Frequent Value
### **Concept: `np.bincount()` and `argmax()`**
**Why it is used?**
- Identifies the most common value in a numerical dataset.

**Syntax:**
```python
most_frequent_value = np.bincount(array).argmax()
```

**Example:**
```python
Rating = np.bincount(np.array(df['rating'])).argmax()
print(Rating)
```

## 12. Calculating Correlation Between Two Columns
### **Concept: `np.corrcoef()`**
**Why it is used?**
- Determines the correlation coefficient between two numerical variables.

**Syntax:**
```python
correlation = np.corrcoef(array1, array2)[0, 1]
```

**Example:**
```python
cgpa_package = np.corrcoef(np.array(df['cgpa']), np.array(df['package']))[0, 1]
print(cgpa_package)
```


## 13. Finding the Range of a Column
### **Concept: `np.max()` and `np.min()`**
**Why it is used?**
- Computes the difference between the highest and lowest values.

**Syntax:**
```python
range_value = np.max(array) - np.min(array)
```

**Example:**
```python
Age = np.max(np.array(df['age'])) - np.min(np.array(df['age']))
print(Age)
```


## 14. Counting Locations Based on Multiple Conditions
### **Concept: Boolean Masking and `np.sum()`**
**Why it is used?**
- Filters data using multiple conditions and counts matching rows.

**Syntax:**
```python
count = np.sum((array1 > value1) & (array2 > value2))
```

**Example:**
```python
marks = np.sum((np.array(df['marks']) > 25) & (np.array(df['marks']) > 60))
print(marks)
```


## 15. Counting Unique Values in a Column
### **Concept: `np.unique()`**
**Why it is used?**
- Identifies unique values and counts their occurrences.

**Syntax:**
```python
unique_values = np.unique(array).size
```

**Example:**
```python
unqiue_spots = np.unique(np.array(df['city'])).size
print(unqiue_spots)
```

## 16. Finding the Most Frequent Value
### **Concept: `pd.Series().mode()`**
**Why it is used?**
- Identifies the most common value in a categorical dataset.

**Syntax:**
```python
most_frequent_value = pd.Series(array).mode()[0]
```

**Example:**
```python
common_fruits = pd.Series(np.array(df['Fruits'])).mode()[0]
print(common_fruits)
```

## 17. Summing All Values in a Column
### **Concept: `np.sum()`**
**Why it is used?**
- Computes the total sum of a numerical column.

**Syntax:**
```python
total_sum = np.sum(array)
```

**Example:**
```python
average_students = np.sum((np.array(df['marks']) > 30) & (np.array(df['percentile']) > 35))
print(average_students)

**Example:**
```python
marks = np.sum(np.array(df['marks']))
print(marks)
```