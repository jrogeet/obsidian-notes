---
topic: ""
part: ""
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Reading data from a file

--- 
use `with` to include file in a Python program.
```python
with open("example.txt") as new_file:
	contents = new_file.read()
	print(contents)
```

`new_file` is a file handle/object (similar to a `parameter` in functions).
- a variable, can be named anything

new_file`.read()` returns the contents of the file as a __Single STRING__.
 ```text
"Hello there!\nThis example file contains three lines of text.\nThis is the last line."
```


## Going through the contents of a file

Text files can be thought of as __lists of strings__, each string representing a single line in the file. 
We can go through the list with a `for` loop.
```python
with open("example.txt") as new_file:
    count = 0
    total_length = 0

    for line in new_file:
        line = line.replace("\n", "")
        count += 1
        print("Line", count, line)
        length = len(line)
        total_length += length

print("Total length of lines:", total_length)
```

- `for line in new_file` iterate each lines of text from the file.
- `replace()` - replaces all instances of the substring (`"\n"` in this case to `""`).
