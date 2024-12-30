---
topic: lists
part: "5.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #lists #matrix
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 03 Matrices

--- 
A two-dimensional array, or a ___matrix___, is also a natural application of a list within a list.

For example, the following matrix

![[Pasted image 20230830113504.png]]
could be presented as a two-dimensional list in Python like so:

```python
my_matrix = [[1, 2, 3], [3, 2, 1], [4, 5, 6]]
```

Matrices in Python are lists containing lists, allowing for matrix-like structures and operations.

### Accessing Elements:
- Access elements using double square brackets: ___`my_matrix[row_index][column_index]`___.
- Indices start from zero.
- Example: ___`my_matrix[0][1]`___ refers to the second element in the first row.

```python
my_matrix = [[1, 2, 3], [3, 2, 1], [4, 5, 6]]

print(my_matrix[0][1])
my_matrix[1][0] = 10
print(my_matrix)
```

### Traversing Matrix
Rows of the matrix can be traversed with a ___for loop___.
```python
my_matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

for row in my_matrix:
    print(row)
```

Traverse elements within each row using ___nested loops___.
```python
my_matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

for row in my_matrix:
    print("a new row")
    for element in row:
        print(element)
```