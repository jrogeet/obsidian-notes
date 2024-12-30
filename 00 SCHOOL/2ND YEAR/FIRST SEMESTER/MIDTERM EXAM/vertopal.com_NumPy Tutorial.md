---
jupyter:
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.6.5
  nbformat: 4
  nbformat_minor: 2
---

::: {.cell .markdown}
### Load in NumPy (remember to pip install numpy first)
:::

::: {.cell .code execution_count="1"}
``` {.python}
import numpy as np
```
:::

::: {.cell .markdown}
### The Basics
:::

::: {.cell .code execution_count="24"}
``` {.python}
a = np.array([1,2,3], dtype='int32')
print(a)
```

::: {.output .stream .stdout}
    [1 2 3]
:::
:::

::: {.cell .code execution_count="10"}
``` {.python}
b = np.array([[9.0,8.0,7.0],[6.0,5.0,4.0]])
print(b)
```

::: {.output .stream .stdout}
    [[9. 8. 7.]
     [6. 5. 4.]]
:::
:::

::: {.cell .code execution_count="16"}
``` {.python}
# Get Dimension
a.ndim
```

::: {.output .execute_result execution_count="16"}
    1
:::
:::

::: {.cell .code execution_count="18"}
``` {.python}
# Get Shape
b.shape
```

::: {.output .execute_result execution_count="18"}
    (2, 3)
:::
:::

::: {.cell .code execution_count="32"}
``` {.python}
# Get Type
a.dtype
```

::: {.output .execute_result execution_count="32"}
    dtype('int32')
:::
:::

::: {.cell .code execution_count="31"}
``` {.python}
# Get Size
a.itemsize
```

::: {.output .execute_result execution_count="31"}
    4
:::
:::

::: {.cell .code execution_count="29"}
``` {.python}
# Get total size
a.nbytes
```

::: {.output .execute_result execution_count="29"}
    12
:::
:::

::: {.cell .code execution_count="35"}
``` {.python}
# Get number of elements
a.size
```

::: {.output .execute_result execution_count="35"}
    3
:::
:::

::: {.cell .markdown}
### Accessing/Changing specific elements, rows, columns, etc
:::

::: {.cell .code execution_count="45"}
``` {.python}
a = np.array([[1,2,3,4,5,6,7],[8,9,10,11,12,13,14]])
print(a)
```

::: {.output .stream .stdout}
    [[ 1  2  3  4  5  6  7]
     [ 8  9 10 11 12 13 14]]
:::
:::

::: {.cell .code execution_count="14"}
``` {.python}
# Get a specific element [r, c]
a[1, 5]
```

::: {.output .execute_result execution_count="14"}
    13
:::
:::

::: {.cell .code execution_count="15"}
``` {.python}
# Get a specific row 
a[0, :]
```

::: {.output .execute_result execution_count="15"}
    array([1, 2, 3, 4, 5, 6, 7])
:::
:::

::: {.cell .code execution_count="16"}
``` {.python}
# Get a specific column
a[:, 2]
```

::: {.output .execute_result execution_count="16"}
    array([ 3, 10])
:::
:::

::: {.cell .code execution_count="20"}
``` {.python}
# Getting a little more fancy [startindex:endindex:stepsize]
a[0, 1:-1:2]
```

::: {.output .execute_result execution_count="20"}
    array([2, 4, 6])
:::
:::

::: {.cell .code execution_count="24"}
``` {.python}
a[1,5] = 20

a[:,2] = [1,2]
print(a)
```

::: {.output .stream .stdout}
    [[ 1  2  5  4  5  6  7]
     [ 8  9  5 11 12 20 14]]
    [[ 1  2  1  4  5  6  7]
     [ 8  9  2 11 12 20 14]]
:::
:::

::: {.cell .markdown}
\*3-d example
:::

::: {.cell .code execution_count="25"}
``` {.python}
b = np.array([[[1,2],[3,4]],[[5,6],[7,8]]])
print(b)
```

::: {.output .stream .stdout}
    [[[1 2]
      [3 4]]

     [[5 6]
      [7 8]]]
:::
:::

::: {.cell .code execution_count="30"}
``` {.python}
# Get specific element (work outside in)
b[0,1,1]
```

::: {.output .execute_result execution_count="30"}
    4
:::
:::

::: {.cell .code execution_count="34"}
``` {.python}
# replace 
b[:,1,:] = [[9,9,9],[8,8]]
```

::: {.output .error ename="ValueError" evalue="setting an array element with a sequence."}
    ---------------------------------------------------------------------------
    ValueError                                Traceback (most recent call last)
    <ipython-input-34-db1aebb5daad> in <module>()
          1 # replace
    ----> 2 b[:,1,:] = [[9,9,9],[8,8]]

    ValueError: setting an array element with a sequence.
:::
:::

::: {.cell .code execution_count="33"}
``` {.python}
b
```

::: {.output .execute_result execution_count="33"}
    array([[[1, 2],
            [9, 9]],

           [[5, 6],
            [8, 8]]])
:::
:::

::: {.cell .markdown}
### Initializing Different Types of Arrays
:::

::: {.cell .code execution_count="40"}
``` {.python}
# All 0s matrix
np.zeros((2,3))
```

::: {.output .execute_result execution_count="40"}
    array([[0., 0., 0.],
           [0., 0., 0.]])
:::
:::

::: {.cell .code execution_count="42"}
``` {.python}
# All 1s matrix
np.ones((4,2,2), dtype='int32')
```

::: {.output .execute_result execution_count="42"}
    array([[[1, 1],
            [1, 1]],

           [[1, 1],
            [1, 1]],

           [[1, 1],
            [1, 1]],

           [[1, 1],
            [1, 1]]])
:::
:::

::: {.cell .code execution_count="44"}
``` {.python}
# Any other number
np.full((2,2), 99)
```

::: {.output .execute_result execution_count="44"}
    array([[99., 99.],
           [99., 99.]], dtype=float32)
:::
:::

::: {.cell .code execution_count="49"}
``` {.python}
# Any other number (full_like)
np.full_like(a, 4)
```

::: {.output .execute_result execution_count="49"}
    array([[4, 4, 4, 4, 4, 4, 4],
           [4, 4, 4, 4, 4, 4, 4]])
:::
:::

::: {.cell .code execution_count="56"}
``` {.python}
# Random decimal numbers
np.random.rand(4,2)
```

::: {.output .execute_result execution_count="56"}
    array([[0.07805642, 0.53385716],
           [0.02494273, 0.99955252],
           [0.48588042, 0.91247437],
           [0.27779213, 0.16597751]])
:::
:::

::: {.cell .code execution_count="73"}
``` {.python}
# Random Integer values
np.random.randint(-4,8, size=(3,3))
```

::: {.output .execute_result execution_count="73"}
    array([[-2, -4, -4],
           [ 6,  6,  3],
           [ 3,  2,  2]])
:::
:::

::: {.cell .code execution_count="76"}
``` {.python}
# The identity matrix
np.identity(5)
```

::: {.output .execute_result execution_count="76"}
    array([[1., 0., 0., 0., 0.],
           [0., 1., 0., 0., 0.],
           [0., 0., 1., 0., 0.],
           [0., 0., 0., 1., 0.],
           [0., 0., 0., 0., 1.]])
:::
:::

::: {.cell .code execution_count="82"}
``` {.python}
# Repeat an array
arr = np.array([[1,2,3]])
r1 = np.repeat(arr,3, axis=0)
print(r1)
```

::: {.output .stream .stdout}
    [[1 2 3]
     [1 2 3]
     [1 2 3]]
:::
:::

::: {.cell .code execution_count="89"}
``` {.python}
output = np.ones((5,5))
print(output)

z = np.zeros((3,3))
z[1,1] = 9
print(z)

output[1:-1,1:-1] = z
print(output)
```

::: {.output .stream .stdout}
    [[1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1.]]
    [[0. 0. 0.]
     [0. 9. 0.]
     [0. 0. 0.]]
    [[1. 1. 1. 1. 1.]
     [1. 0. 0. 0. 1.]
     [1. 0. 9. 0. 1.]
     [1. 0. 0. 0. 1.]
     [1. 1. 1. 1. 1.]]
:::
:::

::: {.cell .markdown}
##### Be careful when copying arrays!!!
:::

::: {.cell .code execution_count="98"}
``` {.python}
a = np.array([1,2,3])
b = a.copy()
b[0] = 100

print(a)
```

::: {.output .stream .stdout}
    [1 2 3]
:::
:::

::: {.cell .markdown}
### Mathematics
:::

::: {.cell .code execution_count="111"}
``` {.python}
a = np.array([1,2,3,4])
print(a)
```

::: {.output .stream .stdout}
    [1 2 3 4]
:::
:::

::: {.cell .code execution_count="109"}
``` {.python}
a + 2
```

::: {.output .execute_result execution_count="109"}
    array([5, 6, 7, 8])
:::
:::

::: {.cell .code execution_count="102"}
``` {.python}
a - 2
```

::: {.output .execute_result execution_count="102"}
    array([-1,  0,  1,  2])
:::
:::

::: {.cell .code execution_count="103"}
``` {.python}
a * 2
```

::: {.output .execute_result execution_count="103"}
    array([2, 4, 6, 8])
:::
:::

::: {.cell .code execution_count="104"}
``` {.python}
a / 2
```

::: {.output .execute_result execution_count="104"}
    array([0.5, 1. , 1.5, 2. ])
:::
:::

::: {.cell .code execution_count="118"}
``` {.python}
b = np.array([1,0,1,0])
a + b
```

::: {.output .execute_result execution_count="118"}
    array([1, 0, 3, 0])
:::
:::

::: {.cell .code execution_count="113"}
``` {.python}
a ** 2
```

::: {.output .execute_result execution_count="113"}
    array([ 1,  4,  9, 16], dtype=int32)
:::
:::

::: {.cell .code execution_count="116"}
``` {.python}
# Take the sin
np.cos(a)

```

::: {.output .execute_result execution_count="116"}
    array([ 0.54030231, -0.41614684, -0.9899925 , -0.65364362])
:::
:::

::: {.cell .code execution_count="117"}
``` {.python}
# For a lot more (https://docs.scipy.org/doc/numpy/reference/routines.math.html)
```
:::

::: {.cell .markdown}
##### Linear Algebra
:::

::: {.cell .code execution_count="127"}
``` {.python}
a = np.ones((2,3))
print(a)

b = np.full((3,2), 2)
print(b)

np.matmul(a,b)
```

::: {.output .stream .stdout}
    [[1. 1. 1.]
     [1. 1. 1.]]
    [[2 2]
     [2 2]
     [2 2]]
:::

::: {.output .execute_result execution_count="127"}
    array([[6., 6.],
           [6., 6.]])
:::
:::

::: {.cell .code execution_count="132"}
``` {.python}
# Find the determinant
c = np.identity(3)
np.linalg.det(c)
```

::: {.output .execute_result execution_count="132"}
    1.0
:::
:::

::: {.cell .code execution_count="133"}
``` {.python}
## Reference docs (https://docs.scipy.org/doc/numpy/reference/routines.linalg.html)

# Determinant
# Trace
# Singular Vector Decomposition
# Eigenvalues
# Matrix Norm
# Inverse
# Etc...
```
:::

::: {.cell .markdown}
##### Statistics
:::

::: {.cell .code execution_count="134"}
``` {.python}
stats = np.array([[1,2,3],[4,5,6]])
stats
```

::: {.output .execute_result execution_count="134"}
    array([[1, 2, 3],
           [4, 5, 6]])
:::
:::

::: {.cell .code execution_count="139"}
``` {.python}
np.min(stats)
```

::: {.output .execute_result execution_count="139"}
    1
:::
:::

::: {.cell .code execution_count="141"}
``` {.python}
np.max(stats, axis=1)
```

::: {.output .execute_result execution_count="141"}
    array([3, 6])
:::
:::

::: {.cell .code execution_count="143"}
``` {.python}
np.sum(stats, axis=0)
```

::: {.output .execute_result execution_count="143"}
    array([5, 7, 9])
:::
:::

::: {.cell .markdown}
### Reorganizing Arrays
:::

::: {.cell .code execution_count="151"}
``` {.python}
before = np.array([[1,2,3,4],[5,6,7,8]])
print(before)

after = before.reshape((2,3))
print(after)
```

::: {.output .stream .stdout}
    [[1 2 3 4]
     [5 6 7 8]]
:::

::: {.output .error ename="ValueError" evalue="cannot reshape array of size 8 into shape (2,3)"}
    ---------------------------------------------------------------------------
    ValueError                                Traceback (most recent call last)
    <ipython-input-151-6aa1f4e15729> in <module>()
          2 print(before)
          3 
    ----> 4 after = before.reshape((2,3))
          5 print(after)

    ValueError: cannot reshape array of size 8 into shape (2,3)
:::
:::

::: {.cell .code execution_count="158"}
``` {.python}
# Vertically stacking vectors
v1 = np.array([1,2,3,4])
v2 = np.array([5,6,7,8])

np.vstack([v1,v2,v1,v2])
```

::: {.output .execute_result execution_count="158"}
    array([[1, 2, 3, 4],
           [5, 6, 7, 8],
           [1, 2, 3, 4],
           [5, 6, 7, 8]])
:::
:::

::: {.cell .code execution_count="164"}
``` {.python}
# Horizontal  stack
h1 = np.ones((2,4))
h2 = np.zeros((2,2))

np.hstack((h1,h2))
```

::: {.output .execute_result execution_count="164"}
    array([[1., 1., 1., 1., 0., 0.],
           [1., 1., 1., 1., 0., 0.]])
:::
:::

::: {.cell .markdown}
### Miscellaneous

##### Load Data from File
:::

::: {.cell .code execution_count="179"}
``` {.python}
filedata = np.genfromtxt('data.txt', delimiter=',')
filedata = filedata.astype('int32')
print(filedata)
```

::: {.output .stream .stdout}
    [[  1  13  21  11 196  75   4   3  34   6   7   8   0   1   2   3   4   5]
     [  3  42  12  33 766  75   4  55   6   4   3   4   5   6   7   0  11  12]
     [  1  22  33  11 999  11   2   1  78   0   1   2   9   8   7   1  76  88]]
:::
:::

::: {.cell .markdown}
##### Boolean Masking and Advanced Indexing
:::

::: {.cell .code execution_count="196"}
``` {.python}
(~((filedata > 50) & (filedata < 100)))
```

::: {.output .execute_result execution_count="196"}
    array([[ True,  True,  True,  True,  True, False,  True,  True,  True,
             True,  True,  True,  True,  True,  True,  True,  True,  True],
           [ True,  True,  True,  True,  True, False,  True, False,  True,
             True,  True,  True,  True,  True,  True,  True,  True,  True],
           [ True,  True,  True,  True,  True,  True,  True,  True, False,
             True,  True,  True,  True,  True,  True,  True, False, False]])
:::
:::

::: {.cell .code}
``` {.python}
```
:::

::: {.cell .code}
``` {.python}
```
:::

::: {.cell .code}
``` {.python}
```
:::

::: {.cell .code}
``` {.python}
```
:::

::: {.cell .code}
``` {.python}
```
:::
