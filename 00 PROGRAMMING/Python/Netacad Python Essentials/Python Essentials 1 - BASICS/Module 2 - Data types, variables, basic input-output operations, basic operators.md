# Python Essentials 1:  
Module 2

**Data types, variables, basic input-output operations, basic operators**

In this module, you will learn:

-   how to write and run simple Python programs;
-   what Python literals, operators, and expressions are;
-   what variables are and what are the rules that govern them;
-   how to perform basic input and output operations.
  
![[Pasted image 20220903110837.png]]



```
print("Hello, World!")
```

As you can see, the first program consists of the following parts:

-   the word `print`;
-   an opening parenthesis;
-   a quotation mark;
-   a line of text: `Hello, World!`;
-   another quotation mark;
-   a closing parenthesis.

Each of the above plays a very important role in the code.

# The print() function

Look at the line of code below:

`print("Hello, World!")`  

The word **print** that you can see here is a **function name**. That doesn't mean that wherever the word appears it is always a function name. The meaning of the word comes from the context in which the word has been used.

You've probably encountered the term function many times before, during math classes. You can probably also list several names of mathematical functions, like sine or log.

Python functions, however, are more flexible, and can contain more content than their mathematical siblings.

A function (in this context) is a separate part of the computer code able to:

-   **cause some effect** (e.g., send text to the terminal, create a file, draw an image, play a sound, etc.); this is something completely unheard of in the world of mathematics;
-   **evaluate a value** (e.g., the square root of a value or the length of a given text) and **return it as the function's result**; this is what makes Python functions the relatives of mathematical concepts.

Moreover, many of Python functions can do the above two things together.

Where do the functions come from?

-   They may come **from Python itself**; the print function is one of this kind; such a function is an added value received together with Python and its environment (it is **built-in**); you don't have to do anything special (e.g., ask anyone for anything) if you want to make use of it;
-   they may come from one or more of Python's add-ons named **modules**; some of the modules come with Python, others may require separate installation - whatever the case, they all need to be explicitly connected with your code (we'll show you how to do that soon);
-   you can **write them yourself**, placing as many functions as you want and need inside your program to make it simpler, clearer and more elegant.

The name of the function should be **significant** (the name of the print function is self-evident).

Of course, if you're going to make use of any already existing function, you have no influence on its name, but when you start writing your own functions, you should consider carefully your choice of names.

# The print() function

As we said before, a function may have:

-   an **effect**;
-   a **result**.

There's also a third, very important, function component - the **argument**(s).

Mathematical functions usually take one argument, e.g., sin(x) takes an x, which is the measure of an angle.

Python functions, on the other hand, are more versatile. Depending on the individual needs, they may accept any number of arguments - as many as necessary to perform their tasks. Note: any number includes zero - some Python functions don't need any argument.

`print("Hello, World!")`  

In spite of the number of needed/provided arguments, Python functions strongly demand the presence of **a pair of parentheses** - opening and closing ones, respectively.

If you want to deliver one or more arguments to a function, you place them **inside the parentheses**. If you're going to use a function which doesn't take any argument, you still have to have the parentheses.

Note: to distinguish ordinary words from function names, place **a pair of empty parentheses** after their names, even if the corresponding function wants one or more arguments. This is a standard convention.

The function we're talking about here is `print()`.

Does the `print()` function in our example have any arguments?

Of course it does, but what are they?

# The print() function

The only argument delivered to the `print()` function in this example is a **string**:

`print("Hello, World!")`  

As you can see, the **string is delimited with quotes** - in fact, the quotes make the string - they cut out a part of the code and assign a different meaning to it.

You can imagine that the quotes say something like: the text between us is not code. It isn't intended to be executed, and you should take it as is.

Almost anything you put inside the quotes will be taken literally, not as code, but as **data**. Try to play with this particular string - modify it, enter some new content, delete some of the existing content.

There's more than one way to specify a string inside Python's code, but for now, though, this one is enough.

![[Pasted image 20221208132558.png]]

So far, you have learned about two important parts of the code: the function and the string. We've talked about them in terms of syntax, but now it's time to discuss them in terms of semantics.

# The print() function

The function name (**_print_** in this case) along with the parentheses and argument(s), forms the **function invocation**.

We'll discuss this in more depth soon, but we should just shed a little light on it right now.

`   print("Hello, World!")       `  
  

What happens when Python encounters an invocation like this one below?

`function_name(argument)`  


Let's see:

-   First, Python checks if the name specified is **legal** (it browses its internal data in order to find an existing function of the name; if this search fails, Python aborts the code);
-   second, Python checks if the function's requirements for the number of arguments **allows you to invoke** the function in this way (e.g., if a specific function demands exactly two arguments, any invocation delivering only one argument will be considered erroneous, and will abort the code's execution);
-   third, Python **leaves your code for a moment** and jumps into the function you want to invoke; of course, it takes your argument(s) too and passes it/them to the function;
-   fourth, the function **executes its code**, causes the desired effect (if any), evaluates the desired result(s) (if any) and finishes its task;
-   finally, Python **returns to your code** (to the place just after the invocation) and resumes its execution.

# The print() function

Three important questions have to be answered as soon as possible:

**1. What is the effect the `print()` function causes?**

The effect is very useful and very spectacular. The function:

-   takes its arguments (it may accept more than one argument and may also accept less than one argument)
-   converts them into human-readable form if needed (as you may suspect, strings don't require this action, as the string is already readable)
-   and **sends the resulting data to the output device** (usually the console); in other words, anything you put into the `print()` function will appear on your screen.

No wonder then, that from now on, you'll utilize `print()` very intensively to see the results of your operations and evaluations.

  

**2. What arguments does `print()` expect?**

Any. We'll show you soon that `print()` is able to operate with virtually all types of data offered by Python. Strings, numbers, characters, logical values, objects - any of these may be successfully passed to `print()`.

**3. What value does the `print()` function return?**

None. Its effect is enough.

# The print() function - instructions

We've changed the example a bit - we've added one **empty** `print()` function invocation. We call it empty because we haven't delivered any arguments to the function.

You can see it in the editor window. Run the code.

What happens?

If everything goes right, you should see something like this:

`The itsy bitsy spider climbed up the waterspout. Down came the rain and washed the spider out.`

**output**

As you can see, the empty `print()` invocation is not as empty as you may have expected - it does output an empty line, or (this interpretation is also correct) its output is just a newline.

This is not the only way to produce a **newline** in the output console. We're now going to show you another way.

# The print() function - the escape and newline characters

We've modified the code again. Look at it carefully.

There are two very subtle changes - we've inserted a strange pair of characters inside the rhyme. They look like this: `\n`.

  

Interestingly, while **you can see two characters, Python sees one.**

The backslash (`\`) has a very special meaning when used inside strings - this is called **the escape character**.

The word _escape_ should be understood specifically - it means that the series of characters in the string escapes for the moment (a very short moment) to introduce a special inclusion.

In other words, the backslash doesn't mean anything in itself, but is only a kind of announcement, that the next character after the backslash has a different meaning too.

The letter `n` placed after the backslash comes from the word _newline_.

Both the backslash and the _n_ form a special symbol named **a newline character**, which urges the console to start a **new output line**.

Run the code. Your console should now look like this:

`The itsy bitsy spider climbed up the waterspout. Down came the rain and washed the spider out.`

As you can see, two newlines appear in the nursery rhyme, in the places where the `\n` have been used.

# The print() function - the escape and newline characters

This convention has two important consequences:

1. If you want to put just one backslash inside a string, don't forget its escaping nature - you have to double it, e.g., such an invocation will cause an error:

`print("\")`  

while this one won't:

`print("\\")`  

2. Not all escape pairs (the backslash coupled with another character) mean something.

  

Experiment with your code in the editor, run it, and see what happens.

# The print() function - using multiple arguments

So far we have tested the `print()` function behavior with no arguments, and with one argument. It's also worth trying to feed the print() function with more than one argument.

Look at the editor window. This is what we're going to test now:

`print("The itsy bitsy spider" , "climbed up" , "the waterspout.")`  

There is one `print()` function invocation, but it contains **three arguments**. All of them are strings.

The arguments are **separated by commas**. We've surrounded them with spaces to make them more visible, but it's not really necessary, and we won't be doing it anymore.

In this case, the commas separating the arguments play a completely different role than the comma inside the string. The former is a part of Python's syntax, the latter is intended to be shown in the console.

If you look at the code again, you'll see that there are no spaces inside the strings.

Run the code and see what happens.

The console should now be showing the following text:

`The itsy bitsy spider climbed up the waterspout.`

**output**

The spaces, removed from the strings, have appeared again. Can you explain why?

Two conclusions emerge from this example:

-   a `print()` function invoked with more than one argument **outputs them all on one line**;
-   the `print()` function **puts a space between the outputted arguments** on its own initiative.
# The print() function - the positional way of passing the arguments

Now that you know a bit about `print()` function customs, we're going to show you how to change them.

You should be able to predict the output without running the code in the editor.

The way in which we are passing the arguments into the `print()` function is the most common in Python, and is called **the positional way** (this name comes from the fact that the meaning of the argument is dictated by its position, e.g., the second argument will be outputted after the first, not the other way round).

Run the code and check if the output matches your predictions

# The print() function - the keyword arguments

Python offers another mechanism for the passing of arguments, which can be helpful when you want to convince the `print()` function to change its behavior a bit.

We aren't going to explain it in depth right now. We plan to do this when we talk about functions. For now, we simply want to show you how it works. Feel free to use it in your own programs.

The mechanism is called **keyword arguments**. The name stems from the fact that the meaning of these arguments is taken not from its location (position) but from the special word (keyword) used to identify them.

The `print()` function has two keyword arguments that you can use for your purposes. The first of them is named `end`.

In the editor window you can see a very simple example of using a keyword argument.

In order to use it, it is necessary to know some rules:

-   a keyword argument consists of three elements: a **keyword** identifying the argument (`end` here); an **equal sign** (`=`); and a **value** assigned to that argument;
-   any keyword arguments have to be put **after the last positional argument** (this is very important)

  

In our example, we have made use of the `end` keyword argument, and set it to a string containing one space.

Run the code to see how it works.

The console should now be showing the following text:

`My name is Python. Monty Python.`

**output**

As you can see, the `end` keyword argument determines the characters the print() function sends to the output once it reaches the end of its positional arguments.

The default behavior reflects the situation where the `end` keyword argument is **implicitly** used in the following way: `end="\n"`.

