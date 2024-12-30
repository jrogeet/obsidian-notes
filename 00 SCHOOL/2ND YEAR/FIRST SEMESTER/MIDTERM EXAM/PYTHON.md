# Numpy
## What is NumPy?

NumPy is a Python library used for working with arrays.

It also has functions for working in domain of linear algebra, fourier transform, and matrices.

NumPy was created in **`2005`** by **`Travis Oliphant`**. It is an open source project and you can use it freely.

NumPy stands for **`Numerical Python.`**

---

## Why Use NumPy?

In Python we have lists that serve the purpose of arrays, but they are slow to process.

NumPy aims to provide an array object that is up to 50x faster than traditional Python lists.

The array object in NumPy is called `ndarray`, it provides a lot of supporting functions that make working with `ndarray` very easy.

Arrays are very frequently used in data science, where speed and resources are very important.
## Why is NumPy Faster Than Lists?

NumPy arrays are stored at one continuous place in memory unlike lists, so processes can access and manipulate them very efficiently.

This behavior is called locality of reference in computer science.

This is the main reason why NumPy is faster than lists. Also it is optimized to work with latest CPU architectures.

---

## Which Language is NumPy written in?

NumPy is a Python library and is written partially in Python, but most of the parts that require fast computation are written in C or C++.

## NumPy as np

NumPy is usually imported under the `np` alias.

**alias:** In Python alias are an alternate name for referring to the same thing.

Create an alias with the `as` keyword while importing:

import numpy as np

Now the NumPy package can be referred to as `np` instead of `numpy`.

### Example

```python
import numpy as np  
  
arr = np.array([1, 2, 3, 4, 5])  
  
print(arr)
```

## Create a NumPy ndarray Object

NumPy is used to work with arrays. The array object in NumPy is called `ndarray`.

We can create a NumPy `ndarray` object by using the `array()` function.

### Example

```python
import numpy as np  
  
arr = np.array([1, 2, 3, 4, 5])  
  
print(arr)  
  
print(type(arr))
```


**type():** This built-in Python function tells us the type of the object passed to it. Like in above code it shows that `arr` is `numpy.ndarray` type.

To create an `ndarray`, we can pass a list, tuple or any array-like object into the `array()` method, and it will be converted into an `ndarray`:

### Example

Use a tuple to create a NumPy array:

```python
import numpy as np  
  
arr = np.array((1, 2, 3, 4, 5))  
  
print(arr)
```

### 0-D Array
```python
import numpy as np  
  
arr = np.array(42)  
  
print(arr)
```
### 1-D Array
An array that has 0-D arrays as its elements is called uni-dimensional or 1-D array.

These are the most common and basic arrays.
```python
import numpy as np  
  
arr = np.array([1, 2, 3, 4, 5])  
  
print(arr)
```
### 2-D Array
An array that has 1-D arrays as its elements is called a 2-D array.

These are often used to represent matrix or 2nd order tensors.
**`2D ARRAY HAS 1 BRACKET BEFORE AND AFTER THE ARRAYS`**
```python
import numpy as np  
  
arr = np.array([[1, 2, 3], [4, 5, 6]])  
  
print(arr)
```
### 3-D Array
An array that has 2-D arrays (matrices) as its elements is called 3-D array.

These are often used to represent a 3rd order tensor.
**`3D ARRAY HAS 2 BRACKETS BEFORE AND AFTER THE ARRAYS`**
```python
import numpy as np  
  
arr = np.array([[[1, 2, 3], [4, 5, 6]], [[1, 2, 3], [4, 5, 6]]])  
  
print(arr)
```

