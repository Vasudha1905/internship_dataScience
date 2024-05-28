# Questions related to numpy and pandas

### Q1) What is the key difference between NumPy arrays and Pandas Series?
* numpy arrays can have multiple dimensions whereas Pandas series has only one dimension

```
# x has i dimension and y has 2 dimensions
import numpy as np
import pandas as pd 
x=pd.Series([1,2,3,4])
x.ndim
y=np.array([[1,2,3,4],[5,6,7,8]])
y.ndim
```
### Q2) How would you select the last three elements of a NumPy array?

```
x=np.array([1,2,3,4])
x[-3:]
```
```
y=np.array([[1,2,3,4],[5,6,7,8]])
y[1,-3:]
```

### Q3) Explain the purpose of the `DataFrame.groupby()` function in pandas.
* The dataframe groupby function allows us to group the rows togehter on the basis of similar values in a column
```
df=pd.DataFrame({'student':['A','B','C'],'class':[10,12,10]})
# group the students on the basis of class.
x=df.groupby('class')
# getting list of students in class 10
x.get_group(10)
```

### Q4) What is broadcasting in NumPy? Provide an example.
* perfroming arithmetic operations of arrays of diffrent size and dimensions is broadcasting
```
a= np.array([[1,2,3],[4,5,6]])
b=np.array([10,20,30])
# a is 2 dimensional and b is 1 dimensional. broadcasting allows us to add
a+b
```

### Q5) How can you handle missing or null values in a pandas DataFrame?
* we can handle missing or null values by
    * replacing them with some other value or 0
    * removing them
```
df1 = pd.DataFrame([1,2,3,4,5],index=['a','b','c','d','e'])
df2 = pd.DataFrame([10,20,30,40,50],index=['c','e','f','g','h'])
df3=df1+df2
df3

# removing rows with na
df3.dropna()

# replacing na with 0
df3.fillna(0)
```

### What is the purpose of the np.random.seed() function in NumPy?
* it is used to generate the same set of random numbers everytime the code runs
```
np.random.seed(2)
np.random.randint(2,100,5)
```
```
np.random.seed(2)
np.random.randint(2,100,5)
```

### Explain the difference between `iloc[]` and `loc[]` in pandas.
* iloc[] uses only index for locating and loc[] uses the label 
```
df=pd.DataFrame({'student':['A','B','C'],'class':[10,12,10]},index=['a','b','c'])
df.loc['a']
df.iloc[0]
```

###  Q8) How would you concatenate two pandas DataFrames vertically?
* we use the concat() function
```
df1 = pd.DataFrame([1,2])
df2 = pd.DataFrame([10,20,30])
pd.concat([df1,df2], ignore_index=True)
```

### Q9) What are the advantages of using pandas over traditional Python data structures like lists and dictionaries?
* pandas allows us to structure our data into tables using dataframes
* dataframes have an index whereas dictionary does not
* lists are one dimentional whereas dataframes are 2 dimensional
* It is easier to alter data in pandas
* we can provide column and row labels using pandas

###  Q10) How can you rename a specific column in a pandas DataFrame?
* we can use the rename() function
```
df=pd.DataFrame({'student':['A','B','C'],'class':[10,12,10]},index=['a','b','c'])
df.rename(columns={'student':'student name'})
```

