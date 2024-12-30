Author: [Alsweigart](https://alsweigart.com/)
Type: Book/Website
Topics: #python #keyword #keywordarguments 
Link: [Automate boring stuff with Python](https://automatetheboringstuff.com/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] [[015 Functions|Functions]] 

---
# Keyword Arguments
Most arguments are identified by their position in the function call.

For example, ***random.randint(1, 10)*** will return random integer between ***1*** and ***10*** because first argument is low end of the range and second argument is the high end.

while ***random.randint(10, 1)*** wil result to an error.

But, rather than through their position, **keyword arguments** are identified by the keyword put before them in the function call.

Keyword arguments are often used for _optional parameters_.

***print()*** function has the optional parameters:
***end*** - to specify what should be printed at the **end** of its argument and 
***sep*** - to specify what should be printed **between** its arguments (**separating them**).

## end Keyword

```python
print('Hello')  
print('World')
```
The output of this would automatically add a Newline character after the ***print('Hello')***.


```python
print('Hello', end='')  
print('World')
```
But, we can change the newline character to a different string with ***end*** keyword.

## sep Keyword

```python
print('cats', 'dogs', 'mice')
```
When you pass multiple string values to print(), the function will automatically separate them with a single space.


```python
print('cats', 'dogs', 'mice', sep=',')
```
Replace the default separating string by passing the ***sep*** keyword argument a different string.