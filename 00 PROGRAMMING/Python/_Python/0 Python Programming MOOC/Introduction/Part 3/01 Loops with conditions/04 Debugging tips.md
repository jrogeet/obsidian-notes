---
topic: loops with conditions
part: "3.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #tips 
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 04 Debugging tips

--- 
## Debugging and Testing Techniques

When writing more complex programs like the one in the upcoming exercise, it's common to encounter bugs that require testing and debugging. Here's a strategy to improve your debugging process:

### Initial Attempts and Testing

When starting a program, you might have an initial version with input reading, loop structure, and a basic condition. However, this code might not work as expected on the first try.

To speed up testing, consider hard-coding inputs instead of typing them manually every time:

```python
# let's hard-code the input value for testing
limit = 8  # int(input("Upper limit"))
number = 1
while number == limit:
    # more code
```

### Debugging with Print Statements

Print statement debugging is a powerful technique to uncover the source of bugs. As programs become more complex, debugging becomes crucial. Place print statements strategically in your code to track the program's execution flow and variable values.

### Python Tutor for Visualization

Besides print statements, tools like Python Tutor's visualization website can aid in debugging. This tool lets you execute code step by step, showing variable values at each stage. It helps you understand how your program works and identify issues.

As your programming skills grow, mastering debugging techniques becomes essential. Debugging will likely become a significant part of your programming practice, especially as you work on more complex projects.


The slightly broken code from the debugging example in the [previous section](https://programming-23.mooc.fi/part-2/4-simple-loops) is visualised with Python Tutor in the following image:

![[Pasted image 20230828183035.png]]
The red arrow points to where the execution of the program is at the moment. The tool displays what has been printed out so far, and also shows the value each variable has at each step. The execution moves forward line by line as you press _Next_.

All you need to do to use the visualisation tool is to copy your code and paste it into the [code window](http://www.pythontutor.com/visualize.html#mode=edit) of the tool. The tool does have some limitations compared to the version of Python used on this course. If you come across any cryptic error messages, it may be better to try some other debugging method.

More experienced programmers are rarely heavy users of the visualisation tool, but for a beginner it can be a valuable aid. Programming as a discipline has little room for luck or chance. It is essential that a programmer understands what values are created by their code at any given moment in the execution. If the values stored in variables are not as expected, there is most likely a bug in the program.

The visualisation tool and debugging print statements are both great ways for a programmer to see with their own eyes that a program does exactly what was expected of it.
