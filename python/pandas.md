# Pandas

* Python Library
* For data manipulation and analysis
* Made out of NumPy

## Series Data

```python
import  pandas as pd

data = pd.Series([1,2,3,4])
print(data)
"""
0 1
1 2
2 3
3 4
dtype: int64
"""

# Series has the values as ndarray
print(type(data)) # <class 'pandas.core.series.Series'>
print(data.values) # [1 2 3 4]
print(type(data.values)) # <class 'numpy.ndarray'>
```
Chaning the dtype
```python
data = pd.Series([1,2,3,4], dtype = "float")
print(data.type) # float64
```
Assigning Index and Accessing the values using Index
```python
data = pd.Series([1,2,3,4], index = ['a', 'b','c','d'])
data['c'] = 5
"""
a 1
b 2
c 5
d 4
dtype: int64
"""
```
Can generate Series using Dictionary
```python
pop_dict = {'china': 141500, 'japan': 12718, 'korea': 5180}
population = pd.Series(pop_dict)
"""
china 141500
japan 12718
korea 5180
dtype: int64
"""
```
## DataFrame
* Many Series are combined to make DataFrame with rows and columns

* Using many series to make a DataFrame
```python
# Dictionary for population
pop_dict = {'china': 141500, 'japan': 12718, 'korea': 5180}
population = pd.Series(pop_dict)
# Dictionary for GDP
gdp_dict = {'china': 1, 'japan': 2, 'korea': 3}
gdp = pd.Series(gdp_dict)

# DataFrame
country = pd.DataFrame({'gdp': gdp, 'population': population})
"""
      gdp     population
china   1       141500
japan   2       12718
korea   3       5180
"""
```
*Using Dictionary to make DataFrame
```python
data = {'Name': ['A', 'B', 'C']}, 'age': [1, 2, 3], 'school': ['a', 'b', 'c']
person = pd.DataFrame(data)
person = person.set_index('person')
"""
person
---------------
A     1     a
B     2     b
C     3     c
"""
```