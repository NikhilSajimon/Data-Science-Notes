
##  NumPy: Numerical Python

NumPy is a core Python library for numerical computing. It provides fast, memory-efficient arrays and supports vectorized operations for high-performance data processing.

---

###  Array Creation

Arrays are the fundamental data structure in NumPy, used for storing homogeneous numerical data.

```python
np.array([1, 2, 3])                     # 1D array  
np.array([[1, 2], [3, 4]])              # 2D array  
np.zeros((2, 3))                        # Array of zeros  
np.ones((3, 3))                         # Array of ones  
np.eye(3)                               # Identity matrix  
```

---

###  Array Attributes

NumPy arrays expose metadata useful for debugging and optimization.

- `.shape` returns the dimensions of the array  
- `.ndim` returns the number of dimensions  
- `.size` returns the total number of elements  
- `.dtype` returns the data type of elements  

---

###  Indexing and Slicing

Array elements are accessed using zero-based indexing and slicing syntax.

```python
a[0]           # First element  
a[1:3]         # Slice from index 1 to 2  
b[0, 1]        # Element at row 0, column 1  
```

---

###  Mathematical Operations

NumPy supports element-wise operations and mathematical functions.

```python
a + 10         # Add scalar  
a * 2          # Multiply scalar  
np.sqrt(a)     # Square root  
np.mean(a)     # Mean  
np.sum(a)      # Sum  
np.dot(a, a)   # Dot product  
```

---

###  Broadcasting

Broadcasting allows operations between arrays of different shapes by automatically expanding dimensions.

```python
a = np.array([1, 2, 3])  
b = np.array([[1], [2], [3]])  
a + b                      # Broadcasted addition  
```

---

###  Random Number Generation

NumPy provides utilities for generating random data used in simulations and model initialization.

```python
np.random.rand(3, 2)       # Uniform distribution  
np.random.randn(3, 2)      # Normal distribution  
np.random.randint(0, 10, 5)  # Random integers  
```

---

## Pandas: Data Analysis Toolkit

Pandas is a high-level library built on NumPy for data manipulation and analysis. It introduces Series and DataFrame objects for handling labeled and tabular data.

---

###  Core Data Structures

- `Series` represents a one-dimensional labeled array  
- `DataFrame` represents a two-dimensional labeled table  

```python
pd.Series([10, 20, 30], index=['a', 'b', 'c'])  
pd.DataFrame({'name': ['Alice', 'Bob'], 'age': [25, 30]})  
```

---

###  Data I/O

Pandas supports reading and writing data in multiple formats.

```python
pd.read_csv('data.csv')  
df.to_csv('output.csv', index=False)  
pd.read_excel('data.xlsx')  
df.to_excel('output.xlsx', index=False)  
```

---

###  Data Exploration

Basic inspection methods reveal structure, types, and summary statistics.

- `.head()` returns the first few rows  
- `.tail()` returns the last few rows  
- `.info()` shows column types and null counts  
- `.describe()` provides statistical summaries  
- `.shape` returns row and column counts  
- `.columns` lists column names  
- `.dtypes` shows data types  

---

###  Selection and Filtering

Data is accessed using column names, row indices, and boolean conditions.

```python
df['age']                     # Single column  
df[['name', 'city']]          # Multiple columns  
df.loc[0]                     # Row by label  
df.iloc[0]                    # Row by index  
df[df['age'] > 30]            # Conditional filter  
```

---

###  Data Cleaning

Pandas provides tools for handling missing values and duplicates.

- `.isnull()` identifies missing values  
- `.dropna()` removes rows with missing values  
- `.fillna(value)` replaces missing values  
- `.duplicated()` detects duplicates  
- `.drop_duplicates()` removes duplicate rows  

---

###  Feature Engineering

New columns are derived from existing data using transformations and binning.

```python
df['age_group'] = pd.cut(df['age'], bins=[0, 30, 40], labels=['Young', 'Mid'])  
df['name_length'] = df['name'].apply(len)  
```

---

###  Grouping and Aggregation

Grouped operations summarize data by categories.

```python
df.groupby('city')['age'].mean()  
df.groupby('city').agg({'age': ['mean', 'max'], 'name': 'count'})  
```

---

###  Merging and Joining

Multiple datasets are combined using keys and index alignment.

```python
pd.merge(df1, df2, on='id', how='inner')  
df1.join(df2.set_index('id'), on='id')  
```

---

###  Sorting and Ranking

Data is ordered and ranked for analysis and reporting.

```python
df.sort_values('age', ascending=False)  
df['rank'] = df['age'].rank()  
```

---

###  Time Series Handling

Datetime functionality supports indexing, resampling, and rolling analysis.

```python
df['date'] = pd.to_datetime(df['date'])  
df.set_index('date', inplace=True)  
df.resample('M').mean()  
```

---
