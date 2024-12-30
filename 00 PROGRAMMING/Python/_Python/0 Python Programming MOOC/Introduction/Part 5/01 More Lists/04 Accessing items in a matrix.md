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
# 04 Accessing items in a matrix

--- 
Accessing a single row within a matrix is simple - just choose the desired row. The following function calculates the sum of the elements on a chosen row:

```python
def sum_of_row(my_matrix, row_no: int):
    # choose the desired row from within the matrix
    row = my_matrix[row_no]
    row_sum = 0
    for item in row:
        row_sum += item

    return row_sum

m = [[4, 2, 3, 2], [9, 1, 12, 11], [7, 8, 9, 5], [2, 9, 15, 1]]

my_sum = sum_of_row(m, 1)
print(my_sum) # prints out 33 (which equals 9 + 1 + 12 + 11)
```

Working with columns within a matrix is slightly more complicated, as the matrix is stored by rows:

```python
def sum_of_column(my_matrix, column_no: int):
    # go through each row and select the item at the chosen position
    column_sum = 0
    for row in my_matrix:
        column_sum += row[column_no]

    return column_sum

m = [[4, 2, 3, 2], [9, 1, 12, 11], [7, 8, 9, 5], [2, 9, 15, 1]]

my_sum = sum_of_column(m, 2)
print(my_sum) # prints out 39 (which equals 3 + 12 + 9 + 15)
```

The column handled here consists of the elements at index 2 on _each row_.

Changing the value of a single element within the matrix is simple: choose a row within the matrix, and then a column within the row:

```python
def change_value(my_matrix, row_no: int, column_no: int, new_value: int):
    # choose the desired row
    row = my_matrix[row_no]
    # select the correct item within the row
    row[column_no] = new_value

m = [[4, 2, 3, 2], [9, 1, 12, 11], [7, 8, 9, 5], [2, 9, 15, 1]]

print(m)
change_value(m, 2, 3, 1000)
print(m)
```

### Modifying Matrix Elements
When modifying matrix elements, directly accessing elements by their indexes is necessary, as iterating through a matrix with a simple ___`for`___ loop won't allow modifications within the loop.

### Iterating and Modifying:
- Use nested loops and index tracking to iterate and modify matrix elements.
- The outer loop iterates over rows, and the inner loop iterates over elements within each row.
- Use the `range` function to generate indexes for iteration.
```python
m = [[1,2,3], [4,5,6], [7,8,9]]

for i in range(len(m)): # using the number of rows in the matrix
    for j in range(len(m[i])): # using the number of items on each row 
        m[i][j] += 1

print(m)
```
Sample output:
```
[[2, 3, 4], [5, 6, 7], [8, 9, 10]]
```

By tracking row and element indexes, you can effectively modify matrix elements while traversing through them. This approach ensures that modifications are applied to the correct positions in the matrix.