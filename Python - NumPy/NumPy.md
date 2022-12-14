## NumPy

* Numerical Python
* a library for the Python programming language, adding support for large, __multi-dimensional arrays__ and matrices, along with a large collection of high-level mathematical functions to operate on these arrays
* Most of the datas could be seen as array of numbers
* Fast calculation and low memory compared to python lists

### Using NumPy
```python
import numpy as np

npArr = np.array(range(5))
print(npArr) # [1 2 3 4 5] no commas
print(type(npArr)) # <class 'numpy.ndarray'> # ndarray: nth dimensional array
```
* Can store only one type of variables in the array
* Getting the data type: .dtype
* Changing the data type: .astype()
```python
arr = np.array([0, 1, 2, 3, 4], dtype=float)
print(arr) # [0. 1. 2. 3. 4.] # in float
print(arr.dtype) # float64, returns the dtype of arr
print(arr.astype(int)) # [0 1 2 3 4], changing the dtype
```

dytpe:
* int: i, int_, int32, int64, i8
* float: f, float_ float32, float64, f8
* str: str, U, U32
* bool: ?, bool_

### ndarray

One Dimension
```python
list = [0,1,2,3]
arr = np.array(list)
print(arr.ndim) # 1
print(arr.shape) # (4,)
```

Two Dimension
```python
list = [[0,1,2],[3,4,5]]
arr = np.array(list)
print(arr.ndim) # 2
print(arr.shape) # (2,3) 2 row and 3 column
```
### Changing Shape, Size, and Length
```python
arr = np.array([0,1,2,3,4,5])
print("arr.shape : {}".format(arr.shape)) # arr.shape : (6,)
print("Size : {}".format(arr.size)) # Size : 6
print("Length : {}".format(len(arr))) # Length : 6

arr.shape = 3, 2
print("arr.shape : {}".format(arr.shape)) # arr.shape : (3,2)
print("Size : {}".format(arr.size)) # Size : 6
print("Length : {}".format(len(arr))) # Length : 3
```

### Printing the ndarray
```python
print(nameOfNumpy[2,3]) # prints elements in index (2,3)
print(nameOfNumpy[0:2, 1:4]) # prints elements in index 0 to 1 and 1 to 3
print(nameOfNumpy[5]) # prints element in index 5
```

### Indexing & Slicing
* Indexing: Finding the data/index
```python
x = np.arrange(7) # [0 1 2 3 4 5 6]
print(x[3]) # 3
print(x[7]) # Error
x[0] = 10 # [10 1 2 3 4 5 6]

x2 = np.arrange(1, 13, 1) # 1 to 13 and increasing by 1
x2.shape = 3, 4 # 3 rows and 4 columns
print(x2) """ 
           [[1 2 3 4]
           [5 6 7 8]
           [9 10 11 12]]
           """
print(x[2,3]) # 12
```
* Slicing: brining a portion using index values
```python
x = np.arrage(7)
print(x) # [0 1 2 3 4 5 6]
print(x[1:4]) # [1 2 3]
print(x[1:]) # [1 2 3 4 5 6]
print(x[:4]) # [0 1 2 3]
print(x[::2]) # [0 2 4 6] 2 space between

x2 = np.arrage(1, 13, 1) # 1 to 13 increasing by 1
x,shape = 3,4
print(x) """ 
           [[1 2 3 4]
           [5 6 7 8]
           [9 10 11 12]]
           """
# 1:2 means row 1, :2:3 means each 2 and increasing by 3
print(x[1:2, :2:3]) # [[5]]
print(x[1:,:2]) # [[5 6]
                  [9 10]]
```

### Boolean Indexing
* Using boolean mask, which is a mask array consisted of True and False
```python
x = np.arrage(7)
print(x) # [0 1 2 3 4 5 6]
# True if smaller than 3, False if not True
print(x < 3) # [True True True False False False False]
print(x > 7) # [False False False False False False False]

print(x[x < 3]) # [0 1 2]
# prints even numbers
print(x[x % 2 == 0]) # [0 2 4 6]
```

### Fancy Indexing
```python
x = np.arrange(7)
print(x) # [0 1 2 3 4 5 6]
# what values are there in index 1, 3, and 5
print(x[[1, 3, 5]]) # [1 3 5]

x2 = np.arrage(1, 13, 1).reshape(3,4)
print(x) """ 
           [[1 2 3 4]
           [5 6 7 8]
           [9 10 11 12]]
           """
# print row 0 and row 2
print(x[[0, 2]]) """
                 [[1 2 3 4]
                 [9 10 11 12]]
                 """
# row 1 and column 2
print(x[1:2, 2]) # [7]
# row 0 and row 2, column 2
print(x[[0,2], 2]) # [3 11]
# row 0 and row 2, column 0 to 1
print(x[[0,2],:2]) """
                   [[1 2]
                   [9 10]]
                   """
```
