
# Python Essentials 2:  
Module 4

**Miscellaneous**

In this module, you will learn about:

-   Generators, iterators and closures;
-   Working with file-system, directory tree and files;
-   Selected Python Standard Library modules (_os_, _datetime_, _time_, and _calendar_.)
![[Pasted image 20221224132229.png]]
# Generators - where to find them

**Generator** - what do you associate this word with? Perhaps it refers to some electronic device. Or perhaps it refers to a heavy and serious machine designed to produce power, electrical or other.

A Python generator is **a piece of specialized code able to produce a series of values, and to control the iteration process**. This is why generators are very often called **iterators**, and although some may find a very subtle distinction between these two, we'll treat them as one.

You may not realize it, but you've encountered generators many, many times before. Take a look at the very simple snippet:

`   for i in range(5):  print(i)       `  

The `range()` function is, in fact, a generator, which is (in fact, again) an iterator.

What is the difference?

A function returns one, well-defined value - it may be the result of a more or less complex evaluation of, e.g., a polynomial, and is invoked once - only once.

A generator **returns a series of values**, and in general, is (implicitly) invoked more than once.

In the example, the `range()` generator is invoked six times, providing five subsequent values from zero to four, and finally signaling that the series is complete.

The above process is completely transparent. Let's shed some light on it. Let's show you the **iterator protocol**.

```python
for i in range(5):
    print(i)
```
# Generators - where to find them: continued

The **iterator protocol is a way in which an object should behave to conform to the rules imposed by the context of the `for` and `in` statements**. An object conforming to the iterator protocol is called an **iterator**.

An iterator must provide two methods:

-   `__iter__()` which should **return the object itself** and which is invoked once (it's needed for Python to successfully start the iteration)
-   `__next__()` which is intended to **return the next value** (first, second, and so on) of the desired series - it will be invoked by the `for`/`in` statements in order to pass through the next iteration; if there are no more values to provide, the method should **raise the `StopIteration` exception**.

Does it sound strange? Not at all. Look at the example in the editor.

We've built a class able to iterate through the first `n` values (where `n` is a constructor parameter) of the Fibonacci numbers.

Let us remind you - the Fibonacci numbers (Fibi) are defined as follows:

Fib1 = 1  
Fib2 = 1  
Fibi = Fibi-1 + Fibi-2

In other words:

-   the first two Fibonacci numbers are equal to 1;
-   any other Fibonacci number is the sum of the two previous ones (e.g., Fib3 = 2, Fib4 = 3, Fib5 = 5, and so on)

Let's dive into the code:

-   lines 2 through 6: the class constructor prints a message (we'll use this to trace the class's behavior), prepares some variables (`__n` to store the series limit, `__i` to track the current Fibonacci number to provide, and `__p1` along with `__p2` to save the two previous numbers);
  
-   lines 8 through 10: the `__iter__` method is obliged to return the iterator object itself; its purpose may be a bit ambiguous here, but there's no mystery; try to imagine an object which is not an iterator (e.g., it's a collection of some entities), but one of its components is an iterator able to scan the collection; the `__iter__` method should **extract the iterator and entrust it with the execution of the iteration protocol**; as you can see, the method starts its action by printing a message;
  
-   lines 12 through 21: the `__next__` method is responsible for creating the sequence; it's somewhat wordy, but this should make it more readable; first, it prints a message, then it updates the number of desired values, and if it reaches the end of the sequence, the method breaks the iteration by raising the StopIteration exception; the rest of the code is simple, and it precisely reflects the definition we showed you earlier;
  
-   lines 24 and 25 make use of the iterator.
  

The code produces the following output:

`__init__ __iter__ __next__ 1 __next__ 1 __next__ 2 __next__ 3 __next__ 5 __next__ 8 __next__ 13 __next__ 21 __next__ 34 __next__ 55 __next__`

**output**

Look:

-   the iterator object is instantiated first;
-   next, Python invokes the `__iter__` method to get access to the actual iterator;
-   the `__next__` method is invoked eleven times - the first ten times produce useful values, while the eleventh terminates the iteration.
```python
class Fib:
    def __init__(self, nn):
        print("__init__")
        self.__n = nn
        self.__i = 0
        self.__p1 = self.__p2 = 1

    def __iter__(self):
        print("__iter__")
        return self

    def __next__(self):
        print("__next__")				
        self.__i += 1
        if self.__i > self.__n:
            raise StopIteration
        if self.__i in [1, 2]:
            return 1
        ret = self.__p1 + self.__p2
        self.__p1, self.__p2 = self.__p2, ret
        return ret


for i in Fib(10):
    print(i)

```

# Generators - where to find them: continued

The previous example shows you a solution where the **iterator object is a part of a more complex class**.

The code isn't really sophisticated, but it presents the concept in a clear way.

Take a look at the code in the editor.

We've built the `Fib` iterator into another class (we can say that we've composed it into the `Class` class). It's instantiated along with `Class`'s object.

The object of the class may be used as an iterator when (and only when) it positively answers to the `__iter__` invocation - this class can do it, and if it's invoked in this way, it provides an object able to obey the iteration protocol.

This is why the output of the code is the same as previously, although the object of the `Fib` class isn't used explicitly inside the `for` loop's context.

```python
class Fib:
    def __init__(self, nn):
        self.__n = nn
        self.__i = 0
        self.__p1 = self.__p2 = 1

    def __iter__(self):
        print("Fib iter")
        return self

    def __next__(self):
        self.__i += 1
        if self.__i > self.__n:
            raise StopIteration
        if self.__i in [1, 2]:
            return 1
        ret = self.__p1 + self.__p2
        self.__p1, self.__p2 = self.__p2, ret
        return ret

class Class:
    def __init__(self, n):
        self.__iter = Fib(n)

    def __iter__(self):
        print("Class iter")
        return self.__iter;


object = Class(8)

for i in object:
    print(i)

```

# The yield statement

The iterator protocol isn't particularly difficult to understand and use, but it is also indisputable that the **protocol is rather inconvenient**.

The main discomfort it brings is **the need to save the state of the iteration between subsequent `__iter__` invocations**.

For example, the `Fib` iterator is forced to precisely store the place in which the last invocation has been stopped (i.e., the evaluated number and the values of the two previous elements). This makes the code larger and less comprehensible.

This is why Python offers a much more effective, convenient, and elegant way of writing iterators.

The concept is fundamentally based on a very specific and powerful mechanism provided by the `yield` keyword.

You may think of the `yield` keyword as a smarter sibling of the `return` statement, with one essential difference.

Take a look at this function:

`   def fun(n):  for i in range(n):  return i       `  

It looks strange, doesn't it? It's clear that the `for` loop has no chance to finish its first execution, as the `return` will break it irrevocably.

Moreover, invoking the function won't change anything - the `for` loop will start from scratch and will be broken immediately.

We can say that such a function is not able to save and restore its state between subsequent invocations.

This also means that a function like this **cannot be used as a generator**.

  
  

  

We've replaced exactly one word in the code - can you see it?

`   def fun(n):  for i in range(n):  yield i       `  

We've added `yield` instead of `return`. This little amendment **turns the function into a generator**, and executing the `yield` statement has some very interesting effects.

First of all, it provides the value of the expression specified after the `yield` keyword, just like `return`, but doesn't lose the state of the function.

All the variables' values are frozen, and wait for the next invocation, when the execution is resumed (not taken from scratch, like after `return`).

There is one important limitation: such a **function should not be invoked explicitly** as - in fact - it isn't a function anymore; **it's a generator object**.

The invocation will **return the object's identifier**, not the series we expect from the generator.

Due to the same reasons, the previous function (the one with the `return` statement) may only be invoked explicitly, and must not be used as a generator.

## How to build a generator

Let us show you the new generator in action.

This is how we can use it:

`   def fun(n):  for i in range(n):  yield i  for v in fun(5):  print(v)   `  

Can you guess the output?

Check

`0 1 2 3 4`

# How to build your own generator

What if you need a **generator to produce the first _n_ powers of _2_**?

Nothing easier. Just look at the code below:

`def powers_of_2(n):`

`power = 1`

`for i in range(n):`

`yield power`

`power *= 2`

`for v in powers_of_2(8):`

`print(v)`

Can you guess the output? Copy the code to the editor and run it to check your guesses.

  

**List comprehensions**

Generators may also be used within **list comprehensions**, just like here:

`   def powers_of_2(n):  power = 1  for i in range(n):  yield power  power *= 2  t = [x for x in powers_of_2(5)]  print(t)   `  

Run the example and check the output.

  

**The list() function**

The `list()` function can transform a series of subsequent generator invocations into **a real list**:

`   def powers_of_2(n):  power = 1  for i in range(n):  yield power  power *= 2  t = list(powers_of_2(3))  print(t)   `  

Again, try to predict the output and run the code to check your predictions.

  

**The in operator**

Moreover, the context created by the `in` operator allows you to use a generator, too.

The example shows how to do it:

`   def powers_of_2(n):  power = 1  for i in range(n):  yield power  power *= 2  for i in range(20):  if i in powers_of_2(4):  print(i)   `  

What's the code's output? Run the program and check.

  

**The Fibanacci number generator**

Now let's see a **Fibonacci number generator**, and ensure that it looks much better than the objective version based on the direct iterator protocol implementation.

Here it is:

`   def fibonacci(n):  p = pp = 1  for i in range(n):  if i in [0, 1]:  yield 1  else:  n = p + pp  pp, p = p, n  yield n  fibs = list(fibonacci(10))  print(fibs)   `  

Guess the output (a list) produced by the generator, and run the code to check if you were right.


# More about list comprehensions

You should be able to remember the rules governing the creation and use of a very special Python phenomenon named **list comprehension - a simple and very impressive way of creating lists and their contents**.

In case you need it, we've provided a quick reminder in the editor.

There are two parts inside the code, both creating a list containing a few of the first natural powers of ten.

The former uses a routine way of utilizing the `for` loop, while the latter makes use of the list comprehension and builds the list in situ, without needing a loop, or any other extended code.

It looks like the list is created inside itself - it's not true, of course, as Python has to perform nearly the same operations as in the first snippet, but it is indisputable that the second formalism is simply more elegant, and lets the reader avoid any unnecessary details.

The example outputs two identical lines containing the following text:

`[1, 10, 100, 1000, 10000, 100000] [1, 10, 100, 1000, 10000, 100000]`

**output**

  

Run the code to check if we're right.

```python
list_1 = []

for ex in range(6):
    list_1.append(10 ** ex)

list_2 = [10 ** ex for ex in range(6)]

print(list_1)
print(list_2)

```
# More about list comprehensions: continued

There is a very interesting syntax we want to show you now. Its usability is not limited to list comprehensions, but we have to admit that comprehensions are the ideal environment for it.

It's a **conditional expression - a way of selecting one of two different values based on the result of a Boolean expression**.

Look:

expression_one if condition else expression_two

It may look a bit surprising at first glance, but you have to keep in mind that it is **not a conditional instruction**. Moreover, it's not an instruction at all. It's an operator.

The value it provides is equal to expression_one when the condition is `True`, and expression_two otherwise.

A good example will tell you more. Look at the code in the editor.

The code fills a list with `1`'s and `0`s - if the index of a particular element is odd, the element is set to `0`, and to `1` otherwise.

Simple? Maybe not at first glance. Elegant? Indisputably.

Can you use the same trick within a list comprehension? Yes, you can.

```python
the_list = []

for x in range(10):
    the_list.append(1 if x % 2 == 0 else 0)

print(the_list)

```
# More about list comprehensions: continued

Look at the example in the editor.

Compactness and elegance - these two words come to mind when looking at the code.

So, what do they have in common, generators and list comprehensions? Is there any connection between them? Yes. A rather loose connection, but an unequivocal one.

Just one change can **turn any list comprehension into a generator**.

  

**List comprehensions vs. generators**

Now look at the code below and see if you can find the detail that turns a list comprehension into a generator:

`   the_list = [1 if x % 2 == 0 else 0 for x in range(10)]  the_generator = (1 if x % 2 == 0 else 0 for x in range(10))  for v in the_list:  print(v, end=" ")  print()  for v in the_generator:  print(v, end=" ")  print()   `  

It's the **parentheses**. The brackets make a comprehension, the parentheses make a generator.

The code, however, when run, produces two identical lines:

`1 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0 1 0`

**output**

How can you know that the second assignment creates a generator, not a list?

There is some proof we can show you. Apply the `len()` function to both these entities.

`len(the_list)` will evaluate to `10`. Clear and predictable. `len(the_generator)` will raise an exception, and you will see the following message:

`TypeError: object of type 'generator' has no len()`

**output**

Of course, saving either the list or the generator is not necessary - you can create them exactly in the place where you need them - just like here:

`   for v in [1 if x % 2 == 0 else 0 for x in range(10)]:  print(v, end=" ")  print()  for v in (1 if x % 2 == 0 else 0 for x in range(10)):  print(v, end=" ")  print()   `  

Note: the same appearance of the output doesn't mean that both loops work in the same way. In the first loop, the list is created (and iterated through) as a whole - it actually exists when the loop is being executed.

In the second loop, there is no list at all - there are only subsequent values produced by the generator, one by one.

Carry out your own experiments.
```python
the_list = [1 if x % 2 == 0 else 0 for x in range(10)]

print(the_list)

```
# The lambda function

The `lambda` function is a concept borrowed from mathematics, more specifically, from a part called _the Lambda calculus_, but these two phenomena are not the same.

Mathematicians use _the Lambda calculus_ in many formal systems connected with logic, recursion, or theorem provability. Programmers use the `lambda` function to simplify the code, to make it clearer and easier to understand.

A `lambda` function is a function without a name (you can also call it **an anonymous function**). Of course, such a statement immediately raises the question: how do you use anything that cannot be identified?

Fortunately, it's not a problem, as you can name such a function if you really need, but, in fact, in many cases the `lambda` function can exist and work while remaining fully incognito.

The declaration of the `lambda` function doesn't resemble a normal function declaration in any way - see for yourself:

`lambda parameters: expression`  

Such a clause **returns the value of the expression when taking into account the current value of the current `lambda` argument**.

As usual, an example will be helpful. Our example uses three `lambda` functions, but gives them names. Look at it carefully:

`   two = lambda: 2  sqr = lambda x: x * x  pwr = lambda x, y: x ** y  for a in range(-2, 3):  print(sqr(a), end=" ")  print(pwr(a, two()))   `  
  

  

Let's analzye it:

-   the first `lambda` is an anonymous **parameterless function** that always returns `2`. As we've **assigned it to a variable named `two`**, we can say that the function is not anonymous anymore, and we can use the name to invoke it.
  
-   the second one is a **one-parameter anonymous function** that returns the value of its squared argument. We've named it as such, too.
  
-   the third `lambda` **takes two parameters** and returns the value of the first one raised to the power of the second one. The name of the variable which carries the `lambda` speaks for itself. We don't use `pow` to avoid confusion with the built-in function of the same name and the same purpose.
  

The program produces the following output:

`4 4 1 1 0 0 1 1 4 4`

**output**

This example is clear enough to show how `lambda`s are declared and how they behave, but it says nothing about why they're necessary, and what they're used for, since they can all be replaced with routine Python functions.

Where is the benefit?

# How to use lambdas and what for?

The most interesting part of using lambdas appears when you can use them in their pure form - **as anonymous parts of code intended to evaluate a result**.

Imagine that we need a function (we'll name it `print_function`) which prints the values of a given (other) function for a set of selected arguments.

We want `print_function` to be universal - it should accept a set of arguments put in a list and a function to be evaluated, both as arguments - we don't want to hardcode anything.

Look at the example in the editor. This is how we've implemented the idea.

Let's analyze it. The `print_function()` function takes two parameters:

-   the first, a list of arguments for which we want to print the results;
-   the second, a function which should be invoked as many times as the number of values that are collected inside the first parameter.

Note: we've also defined a function named `poly()` - this is the function whose values we're going to print. The calculation the function performs isn't very sophisticated - it's the polynomial (hence its name) of a form:

f(x) = 2x2 - 4x + 2

The name of the function is then passed to the `print_function()` along with a set of five different arguments - the set is built with a list comprehension clause.

The code prints the following lines:

`f(-2)=18 f(-1)=8 f(0)=2 f(1)=0 f(2)=2`

**output**

Can we avoid defining the `poly()` function, as we're not going to use it more than once? Yes, we can - this is the benefit a lambda can bring.

  

Look at the example below. Can you see the difference?

`   def print_function(args, fun):  for x in args:  print('f(', x,')=', fun(x), sep='')  print_function([x for x in range(-2, 3)], lambda x: 2 * x**2 - 4 * x + 2)   `  

The `print_function()` has remained exactly the same, but there is no `poly()` function. We don't need it anymore, as the polynomial is now directly inside the `print_function()` invocation in the form of a lambda defined in the following way:

`lambda x: 2 * x**2 - 4 * x + 2`

The code has become shorter, clearer, and more legible.

Let us show you another place where lambdas can be useful. We'll start with a description of `map()`, a built-in Python function. Its name isn't too descriptive, its idea is simple, and the function itself is really usable.

```python
def print_function(args, fun):
    for x in args:
        print('f(', x,')=', fun(x), sep='')


def poly(x):
    return 2 * x**2 - 4 * x + 2


print_function([x for x in range(-2, 3)], poly)

```
# Lambdas and the map() function

In the simplest of all possible cases, the `map()` function:

`map(function, list)`

takes two arguments:

-   a function;
-   a list.

The above description is extremely simplified, as:

-   the second `map()` argument may be any entity that can be iterated (e.g., a tuple, or just a generator)
-   `map()` can accept more than two arguments.

The **`map()` function applies the function passed by its first argument to all its second argument's elements, and returns an iterator delivering all subsequent function results**.

You can use the resulting iterator in a loop, or convert it into a list using the `list()` function.

Can you see a role for any lambda here?

Look at the code in the editor - we've used two lambdas in it.

This is the intrigue:

-   build the `list_1` with values from `0` to `4`;
-   next, use `map` along with the first `lambda` to create a new list in which all elements have been evaluated as `2` raised to the power taken from the corresponding element from `list_1`;
-   `list_2` is printed then;
-   in the next step, use the `map()` function again to make use of the generator it returns and to directly print all the values it delivers; as you can see, we've engaged the second `lambda` here - it just squares each element from `list_2`.

Try to imagine the same code without lambdas. Would it be any better? It's unlikely.

```python
list_1 = [x for x in range(5)]
list_2 = list(map(lambda x: 2 ** x, list_1))
print(list_2)

for x in map(lambda x: x * x, list_2):
    print(x, end=' ')
print()

```
# Lambdas and the filter() function

Another Python function which can be significantly beautified by the application of a lambda is `filter()`.

It expects the same kind of arguments as `map()`, but does something different - it **filters its second argument while being guided by directions flowing from the function specified as the first argument** (the function is invoked for each list element, just like in `map()`).

The elements which return `True` from the function **pass the filter** - the others are rejected.

The example in the editor shows the `filter()` function in action.

Note: we've made use of the `random` module to initialize the random number generator (not to be confused with the generators we've just talked about) with the `seed()` function, and to produce five random integer values from `-10` to `10` using the `randint()` function.

The list is then filtered, and only the numbers which are even and greater than zero are accepted.

Of course, it's not likely that you'll receive the same results, but this is what our results looked like:

`[6, 3, 3, 2, -7] [6, 2]`

**output**
```python
from random import seed, randint

seed()
data = [randint(-10,10) for x in range(5)]
filtered = list(filter(lambda x: x > 0 and x % 2 == 0, data))

print(data)
print(filtered)

```
# A brief look at closures

Let's start with a definition: **closure is a technique which allows the storing of values in spite of the fact that the context in which they have been created does not exist anymore**. Intricate? A bit.

Let's analyze a simple example:

`def outer(par): loc = par var = 1 outer(var) print(var) print(loc)`  

The example is obviously erroneous.

The last two lines will cause a NameError exception - neither `par` nor `loc` is accessible outside the function. Both the variables exist when and only when the `outer()` function is being executed.

  

Look at the example in the editor. We've modified the code significantly.

There is a brand new element in it - a function (named `inner`) inside another function (named `outer`).

How does it work? Just like any other function except for the fact that `inner()` may be invoked only from within `outer()`. We can say that `inner()` is `outer()`'s private tool - no other part of the code can access it.

Look carefully:

-   the `inner()` function returns the value of the variable accessible inside its scope, as `inner()` can use any of the entities at the disposal of `outer()`
-   the `outer()` function returns the `inner()` function itself; more precisely, it returns a copy of the `inner()` function, the one which was frozen at the moment of `outer()`'s invocation; the frozen function contains its full environment, including the state of all local variables, which also means that the value of `loc` is successfully retained, although `outer()` ceased to exist a long time ago.

In effect, the code is fully valid, and outputs:

`1`

**output**

The function returned during the `outer()` invocation is a **closure**.
```python
def outer(par):
    loc = par

    def inner():
        return loc
    return inner


var = 1
fun = outer(var)
print(fun())

```
# A brief look at closures: continued

**A closure has to be invoked in exactly the same way in which it has been declared**.

In the example below:

`   def outer(par):  loc = par  def inner():  return loc  return inner  var = 1  fun = outer(var)  print(fun())   `  

the `inner()` function is parameterless, so we have to invoke it without arguments.

Now look at the code in the editor. It is fully possible to **declare a closure equipped with an arbitrary number of parameters**, e.g., one, just like the `power()` function.

This means that the closure not only makes use of the frozen environment, but it can also **modify its behavior by using values taken from the outside**.

This example shows one more interesting circumstance - you can **create as many closures as you want using one and the same piece of code**. This is done with a function named `make_closure()`. Note:

-   the first closure obtained from `make_closure()` defines a tool squaring its argument;
-   the second one is designed to cube the argument.

This is why the code produces the following output:

`0 0 0 1 1 1 2 4 8 3 9 27 4 16 64`

**output**

Carry out your own tests.

```python
def make_closure(par):
    loc = par

    def power(p):
        return p ** loc
    return power


fsqr = make_closure(2)
fcub = make_closure(3)

for i in range(5):
    print(i, fsqr(i), fcub(i))

```
# Key takeaways

  

1. An **iterator** is an object of a class providing at least **two** methods (not counting the constructor!):

-   `__iter__()` is invoked once when the iterator is created and returns the iterator's object **itself**;
-   `__next__()` is invoked to provide the **next iteration's value** and raises the `StopIteration` exception when the iteration **comes to and end**.

  

2. The `yield` statement can be used only inside functions. The `yield` statement suspends function execution and causes the function to return the yield's argument as a result. Such a function cannot be invoked in a regular way – its only purpose is to be used as a **generator** (i.e. in a context that requires a series of values, like a `for` loop.)

  

3. A **conditional expression** is an expression built using the `if-else` operator. For example:

`   print(True if 0 >=0 else False)   `  

outputs `True`.

  

4. A **list comprehension** becomes a **generator** when used inside **parentheses** (used inside brackets, it produces a regular list). For example:

`   for x in (el * 2 for el in range(5)):  print(x)   `  

outputs `02468`.

  

4. A **lambda function** is a tool for creating **anonymous functions**. For example:

`   def foo(x,f):  return f(x)  print(foo(9, lambda x: x ** 0.5))   `  

outputs `3.0`.

  

5. The `map(fun, list)` function creates a **copy** of a `list` argument, and applies the `fun` function to all of its elements, returning a **generator** that provides the new list content element by element. For example:

`   short_list = ['mython', 'python', 'fell', 'on', 'the', 'floor']  new_list = list(map(lambda s: s.title(), short_list))  print(new_list)   `  

outputs `['Mython', 'Python', 'Fell', 'On', 'The', 'Floor']`.

  

6. The `filter(fun, list)` function creates a **copy** of those `list` elements, which cause the `fun` function to return `True`. The function's result is a **generator** providing the new list content element by element. For example:

`   short_list = [1, "Python", -1, "Monty"]  new_list = list(filter(lambda s: isinstance(s, str), short_list))  print(new_list)   `  

outputs `['Python', 'Monty']`.

  

7. A closure is a technique which allows the **storing of values** in spite of the fact that the **context** in which they have been created **does not exist anymore**. For example:

`   def tag(tg):  tg2 = tg  tg2 = tg[0] + '/' + tg[1:]  def inner(str):  return tg + str + tg2  return inner  b_tag = tag('<b>')  print(b_tag('Monty Python'))   `  

outputs `<b>Monty Python</b>`

  

  

**Exercise 1**

What is the expected output of the following code?

`class Vowels: def __init__(self): self.vow = "aeiouy " # Yes, we know that y is not always considered a vowel. self.pos = 0 def __iter__(self): return self def __next__(self): if self.pos == len(self.vow): raise StopIteration self.pos += 1 return self.vow[self.pos - 1] vowels = Vowels() for v in vowels: print(v, end=' ')`  
Check

`a e i o u y`

  
  

**Exercise 2**

Write a **lambda** function, setting the least significant bit of its integer argument, and apply it to the `map()` function to produce the string `1 3 3 5` on the console.

`any_list = [1, 2, 3, 4] even_list = # Complete the line here. print(even_list)`  
Check

`list(map(lambda n: n | 1, any_list))`

  
  

**Exercise 3**

What is the expected output of the following code?

`def replace_spaces(replacement='*'): def new_replacement(text): return text.replace(' ', replacement) return new_replacement stars = replace_spaces() print(stars("And Now for Something Completely Different"))`  
Check

`And*Now*for*Something*Completely*Different`

  

---

**Note**

[PEP 8](https://www.python.org/dev/peps/pep-0008/#programming-recommendations), the Style Guide for Python Code, recommends that **lambdas should not be assigned to variables, but rather they should be defined as functions**.

This means that it is better to use a `def` statement, and avoid using an assignment statement that binds a lambda expression to an identifer. For example:

`# Recommended:`

`def f(x): return 3*x`

`# Not recommended:`

`f = lambda x: 3*x`

Binding lambdas to identifiers generally duplicates the functionality of the `def` statement. Using `def` statements, on the other hand, generates more lines of code.

It is important to understand that reality often likes to draw its own scenarios, which do not necessarily follow the conventions or formal recommendations. Whether you decide to follow them or not will depend on many things: your preferences, other conventions adopted, company internal guidelines, compatibility with existing code, etc. Be aware of this.

# Accessing files from Python code

One of the most common issues in the developer's job is to **process data stored in files** while the files are usually physically stored using storage devices - hard, optical, network, or solid-state disks.

It's easy to imagine a program that sorts 20 numbers, and it's equally easy to imagine the user of this program entering these twenty numbers directly from the keyboard.

It's much harder to imagine the same task when there are 20,000 numbers to be sorted, and there isn't a single user who is able to enter these numbers without making a mistake.

It's much easier to imagine that these numbers are stored in the disk file which is read by the program. The program sorts the numbers and doesn't send them to the screen, but instead creates a new file and saves the sorted sequence of numbers there.

If we want to implement a simple database, the only way to store the information between program runs is to save it into a file (or files if your database is more complex).

  
  

  

In principle, any non-simple programming problem relies on the use of files, whether it processes images (stored in files), multiplies matrices (stored in files), or calculates wages and taxes (reading data stored in files).

![[Pasted image 20221224133100.png]]
You may ask why we have waited until now to show you these issues.

The answer is very simple - Python's way of accessing and processing files is implemented using a consistent set of objects. There is no better moment to talk about it.
## File names

Different operating systems can treat the files in different ways. For example, Windows uses a different naming convention than the one adopted in Unix/Linux systems.

If we use the notion of a canonical file name (a name which uniquely defines the location of the file regardless of its level in the directory tree) we can realize that these names look different in Windows and in Unix/Linux:
![[Pasted image 20221224133122.png]]
As you can see, systems derived from Unix/Linux don't use the disk drive letter (e.g., `C:`) and all the directories grow from one root directory called `/`, while Windows systems recognize the root directory as `\`.

  
  

In addition, Unix/Linux system file names are case-sensitive. Windows systems store the case of letters used in the file name, but don't distinguish between their cases at all.

This means that these two strings: `ThisIsTheNameOfTheFile` and `thisisthenameofthefile` describe two different files in Unix/Linux systems, but are the same name for just one file in Windows systems.

The main and most striking difference is that you have to use **two different separators for the directory names**: `\` in Windows, and `/` in Unix/Linux.

This difference is not very important to the normal user, but is **very important when writing programs in Python**.

To understand why, try to recall the very specific role played by the `\` inside Python strings.

## File names: continued

Suppose you're interested in a particular file located in the directory dir, and named file.

Suppose also that you want to assign a string containing the name of the file.

In Unix/Linux systems, it may look as follows:

`name = "/dir/file"`  

But if you try to code it for the Windows system:

`name = "\dir\file"`  

you'll get an unpleasant surprise: either Python will generate an error, or the execution of the program will behave strangely, as if the file name has been distorted in some way.

In fact, it's not strange at all, but quite obvious and natural. Python uses the `\` as an escape character (like `\n`).

This means that Windows file names must be written as follows:

`name = "\\dir\\file"`  

Fortunately, there is also one more solution. Python is smart enough to be able to convert slashes into backslashes each time it discovers that it's required by the OS.

This means that any the following assignments:

`name = "/dir/file" name = "c:/dir/file"`  

will work with Windows, too.

Any program written in Python (and not only in Python, because that convention applies to virtually all programming languages) does not communicate with the files directly, but through some abstract entities that are named differently in different languages or environments - the most-used terms are **handles** or **streams** (we'll use them as synonyms here).

The programmer, having a more- or less-rich set of functions/methods, is able to perform certain operations on the stream, which affect the real files using mechanisms contained in the operating system kernel.

In this way, you can implement the process of accessing any file, even when the name of the file is unknown at the time of writing the program.

  
  

  

The operations performed with the abstract stream reflect the activities related to the physical file.

![[Pasted image 20221224133142.png]]
  
To connect (bind) the stream with the file, it's necessary to perform an explicit operation.

The operation of connecting the stream with a file is called **opening the file**, while disconnecting this link is named **closing the file**.

Hence, the conclusion is that the very first operation performed on the stream is always `open` and the last one is `close`. The program, in effect, is free to manipulate the stream between these two events and to handle the associated file.

This freedom is limited, of course, by the physical characteristics of the file and the way in which the file has been opened.

Let us say again that the opening of the stream can fail, and it may happen due to several reasons: the most common is the lack of a file with a specified name.

It can also happen that the physical file exists, but the program is not allowed to open it. There's also the risk that the program has opened too many streams, and the specific operating system may not allow the simultaneous opening of more than n files (e.g., 200).

A well-written program should detect these failed openings, and react accordingly.

## File streams

The opening of the stream is not only associated with the file, but should also declare the manner in which the stream will be processed. This declaration is called an **open mode**.

If the opening is successful, the **program will be allowed to perform only the operations which are consistent with the declared open mode**.

There are two basic operations performed on the stream:

-   **read** from the stream: the portions of the data are retrieved from the file and placed in a memory area managed by the program (e.g., a variable);
-   **write** to the stream: the portions of the data from the memory (e.g., a variable) are transferred to the file.

There are three basic modes used to open the stream:

-   **read mode**: a stream opened in this mode allows **read operations only**; trying to write to the stream will cause an exception (the exception is named UnsupportedOperation, which inherits OSError and ValueError, and comes from the io module);
-   **write mode**: a stream opened in this mode allows **write operations only**; attempting to read the stream will cause the exception mentioned above;
-   **update mode**: a stream opened in this mode allows **both writes and reads**.

  
  

  

Before we discuss how to manipulate the streams, we owe you some explanation. **The stream behaves almost like a tape recorder**.

When you read something from a stream, a virtual head moves over the stream according to the number of bytes transferred from the stream.

When you write something to the stream, the same head moves along the stream recording the data from the memory.

Whenever we talk about reading from and writing to the stream, try to imagine this analogy. The programming books refer to this mechanism as the **current file position**, and we'll also use this term.
![[Pasted image 20221224133200.png]]
It's necessary now to show you the object responsible for representing streams in programs.

## File handles

Python assumes that **every file is hidden behind an object of an adequate class**.

Of course, it's hard not to ask how to interpret the word _adequate_.

Files can be processed in many different ways - some of them depend on the file's contents, some on the programmer's intentions.

In any case, different files may require different sets of operations, and behave in different ways.

An object of an adequate class is **created when you open the file and annihilate it at the time of closing**.

Between these two events, you can use the object to specify what operations should be performed on a particular stream. The operations you're allowed to use are imposed by **the way in which you've opened the file**.

  
  

  

In general, the object comes from one of the classes shown here:
![[Pasted image 20221224133213.png]]
Note: you never use constructors to bring these objects to life. The only way you **obtain them is to invoke the function named `open()`**.

The function analyses the arguments you've provided, and automatically creates the required object.

If you want to **get rid of the object, you invoke the method named `close()`**.

The invocation will sever the connection to the object, and the file and will remove the object.

For our purposes, we'll concern ourselves only with streams represented by `BufferIOBase` and `TextIOBase` objects. You'll understand why soon.

## File handles: continued

Due to the type of the stream's contents, **all the streams are divided into text and binary streams**.

The text streams ones are structured in lines; that is, they contain typographical characters (letters, digits, punctuation, etc.) arranged in rows (lines), as seen with the naked eye when you look at the contents of the file in the editor.

This file is written (or read) mostly character by character, or line by line.

The binary streams don't contain text but a sequence of bytes of any value. This sequence can be, for example, an executable program, an image, an audio or a video clip, a database file, etc.

Because these files don't contain lines, the reads and writes relate to portions of data of any size. Hence the data is read/written byte by byte, or block by block, where the size of the block usually ranges from one to an arbitrarily chosen value.

Then comes a subtle problem. In Unix/Linux systems, the line ends are marked by a single character named `LF` (ASCII code 10) designated in Python programs as `\n`.

Other operating systems, especially these derived from the prehistoric CP/M system (which applies to Windows family systems, too) use a different convention: the end of line is marked by a pair of characters, `CR` and `LF` (ASCII codes 13 and 10) which can be encoded as `\r\n`.

![[Pasted image 20221224133229.png]]
This ambiguity can cause various unpleasant consequences.

If you create a program responsible for processing a text file, and it is written for Windows, you can recognize the ends of the lines by finding the `\r\n` characters, but the same program running in a Unix/Linux environment will be completely useless, and vice versa: the program written for Unix/Linux systems might be useless in Windows.

Such undesirable features of the program, which prevent or hinder the use of the program in different environments, are called **non-portability**.

Similarly, the trait of the program allowing execution in different environments is called **portability**. A program endowed with such a trait is called a **portable program**.

## File handles: continued

Since portability issues were (and still are) very serious, a decision was made to definitely resolve the issue in a way that doesn't engage the developer's attention.
![[Pasted image 20221224133243.png]]
It was done at the level of classes, which are responsible for reading and writing characters to and from the stream. It works in the following way:

-   when the stream is open and it's advised that the data in the associated file will be processed as text (or there is no such advisory at all), it is **switched into text mode**;
  
-   during reading/writing of lines from/to the associated file, nothing special occurs in the Unix environment, but when the same operations are performed in the Windows environment, a process called a **translation of newline characters** occurs: when you read a line from the file, every pair of `\r\n` characters is replaced with a single `\n` character, and vice versa; during write operations, every `\n` character is replaced with a pair of `\r\n` characters;
  
-   the mechanism is completely **transparent** to the program, which can be written as if it was intended for processing Unix/Linux text files only; the source code run in a Windows environment will work properly, too;
  
-   when the stream is open and it's advised to do so, its contents are taken as-is, **without any conversion** - no bytes are added or omitted.

  
  
  
  

## Opening the streams

The **opening of the stream** is performed by a function which can be invoked in the following way:

`   stream = open(file, mode = 'r', encoding = None)   `  

Let's analyze it:

-   the name of the function (`open`) speaks for itself; if the opening is successful, the function returns a stream object; otherwise, an exception is raised (e.g., FileNotFoundError **if the file you're going to read doesn't exist**);
  
-   the first parameter of the function (`file`) specifies the name of the file to be associated with the stream;
  
-   the second parameter (`mode`) specifies the open mode used for the stream; it's a string filled with a sequence of characters, and each of them has its own special meaning (more details soon);
  
-   the third parameter (`encoding`) specifies the encoding type (e.g., UTF-8 when working with text files)
  
-   the opening must be the very first operation performed on the stream.

Note: the mode and encoding arguments may be omitted - their default values are assumed then. The default opening mode is reading in text mode, while the default encoding depends on the platform used.

Let us now present you with the most important and useful open modes. Ready?

## Opening the streams: modes

`r` open mode: read

-   the stream will be opened in **read mode**;
-   the file associated with the stream **must exist** and has to be readable, otherwise the `open()` function raises an exception.

`w` open mode: write

-   the stream will be opened in **write mode**;
-   the file associated with the stream **doesn't need to exist**; if it doesn't exist it will be created; if it exists, it will be truncated to the length of zero (erased); if the creation isn't possible (e.g., due to system permissions) the `open()` function raises an exception.

`a` open mode: append

-   the stream will be opened in **append mode**;
-   the file associated with the stream **doesn't need to exist**; if it doesn't exist, it will be created; if it exists the virtual recording head will be set at the end of the file (the previous content of the file remains untouched.)

`r+` open mode: read and update

-   the stream will be opened in **read and update mode**;
-   the file associated with the stream **must exist and has to be writeable**, otherwise the `open()` function raises an exception;
-   both read and write operations are allowed for the stream.

`w+` open mode: write and update

-   the stream will be opened in **write and update** mode;
-   the file associated with the stream **doesn't need to exist**; if it doesn't exist, it will be created; the previous content of the file remains untouched;
-   both read and write operations are allowed for the stream.

  
  

## Selecting text and binary modes

If there is a letter `b` at the end of the mode string it means that the stream is to be opened in the **binary mode**.

If the mode string ends with a letter `t` the stream is opened in the **text mode**.

Text mode is the default behaviour assumed when no binary/text mode specifier is used.

Finally, the successful opening of the file will set the current file position (the virtual reading/writing head) before the first byte of the file **if the mode is not `a`** and after the last byte of file **if the mode is set to `a`**.
![[Pasted image 20221224133346.png]]
**EXTRA**

You can also open a file for its exclusive creation. You can do this using the `x` open mode. If the file already exists, the `open()` function will raise an exception.

## pening the stream for the first time

Imagine that we want to develop a program that reads content of the text file named: C:\Users\User\Desktop\file.txt.

How to open that file for reading? Here's the relevant snippet of the code
```python
try:
    stream = open("C:\Users\User\Desktop\file.txt", "rt")
    # Processing goes here.
    stream.close()
except Exception as exc:
    print("Cannot open the file:", exc)


```
What's going on here?

-   we open the try-except block as we want to handle runtime errors softly;
-   we use the `open()` function to try to open the specified file (note the way we've specified the file name)
-   the open mode is defined as text to read (as **text is the default setting**, we can skip the `t` in mode string)
-   in case of success we get an object from the `open()` function and we assign it to the stream variable;
-   if `open()` fails, we handle the exception printing full error information (it's definitely good to know what exactly happened)

## Pre-opened streams

We said earlier that any stream operation must be preceded by the `open()` function invocation. There are three well-defined exceptions to the rule.

When our program starts, the three streams are already opened and don't require any extra preparations. What's more, your program can use these streams explicitly if you take care to import the `sys` module:

`   import sys       `  

because that's where the declaration of the three streams is placed.

  
  

  

The names of these streams are: `sys.stdin`, `sys.stdout`, and `sys.stderr`.

Let's analyze them:

-   `sys.stdin`

-   stdin (as _standard input_)
-   the `stdin` stream is normally associated with the keyboard, pre-open for reading and regarded as the primary data source for the running programs;
-   the well-known `input()` function reads data from `stdin` by default.

  
-   `sys.stdout`

-   stdout (as _standard output_)
-   the `stdout` stream is normally associated with the screen, pre-open for writing, regarded as the primary target for outputting data by the running program;
-   the well-known `print()` function outputs the data to the `stdout` stream.

  
-   `sys.stderr`

-   stderr (as _standard error output_)
-   the `stderr` stream is normally associated with the screen, pre-open for writing, regarded as the primary place where the running program should send information on the errors encountered during its work;
-   we haven't presented any method to send the data to this stream (we will do it soon, we promise)
-   the separation of `stdout` (useful results produced by the program) from the `stderr` (error messages, undeniably useful but does not provide results) gives the possibility of redirecting these two types of information to the different targets. More extensive discussion of this issue is beyond the scope of our course. The operation system handbook will provide more information on these issues.
## Closing streams

The last operation performed on a stream (this doesn't include the `stdin`, `stdout`, and `stderr` streams which don't require it) should be **closing**.

That action is performed by a method invoked from within open stream object: `stream.close()`.

-   the name of the function is definitely self-commenting: `close()`
-   the function expects exactly no arguments; the stream doesn't need to be opened
-   the function returns nothing but raises IOError exception in case of error;
-   most developers believe that the `close()` function always succeeds and thus there is no need to check if it's done its task properly.  
      
    This belief is only partly justified. If the stream was opened for writing and then a series of write operations were performed, it may happen that the data sent to the stream has not been transferred to the physical device yet (due to mechanism called **caching** or **buffering**).  
      
    Since the closing of the stream forces the buffers to flush them, it may be that the flushes fail and therefore the `close()` fails too.

We have already mentioned failures caused by functions operating with streams but not mentioned a word how exactly we can identify the cause of the failure.

The possibility of making a diagnosis exists and is provided by one of streams' exception component which we are going to tell you about just now.

## Diagnosing stream problems

The `IOError` object is equipped with a property named `errno` (the name comes from the phrase _error number_) and you can access it as follows:

```python
try:
    # Some stream operations.
except IOError as exc:
    print(exc.errno)


```

The value of the `errno` attribute can be compared with one of the predefined symbolic constants defined in the `errno` module.

  
  

  

Let's take a look at some selected **constants useful for detecting stream errors**:

-   `errno.EACCES` → Permission denied  
      
    The error occurs when you try, for example, to open a file with the _read only_ attribute for writing.
  
-   `errno.EBADF` → Bad file number  
      
    The error occurs when you try, for example, to operate with an unopened stream.
  
-   `errno.EEXIST` → File exists  
      
    The error occurs when you try, for example, to rename a file with its previous name.
  
-   `errno.EFBIG` → File too large  
      
    The error occurs when you try to create a file that is larger than the maximum allowed by the operating system.
  
-   `errno.EISDIR` → Is a directory  
      
    The error occurs when you try to treat a directory name as the name of an ordinary file.
  
-   `errno.EMFILE` → Too many open files  
      
    The error occurs when you try to simultaneously open more streams than acceptable for your operating system.
  
-   `errno.ENOENT` → No such file or directory  
      
    The error occurs when you try to access a non-existent file/directory.
  
-   `errno.ENOSPC` → No space left on device  
      
    The error occurs when there is no free space on the media.

The complete list is much longer (it includes also some error codes not related to the stream processing.)

# Diagnosing stream problems: continued

If you are a very careful programmer, you may feel the need to use the sequence of statements similar to those presented in the editor.

Fortunately, there is a function that can dramatically **simplify the error handling code**.

Its name is `strerror()`, and it comes from the `os` module and **expects just one argument - an error number**.

Its role is simple: you give an error number and get a string describing the meaning of the error.

Note: if you pass a non-existent error code (a number which is not bound to any actual error), the function will raise ValueError exception.

Now we can simplify our code in the following way:

`   from os import strerror  try:  s = open("c:/users/user/Desktop/file.txt", "rt")  # Actual processing goes here.  s.close()  except Exception as exc:  print("The file could not be opened:", strerror(exc.errno))   `  

Okay. Now it's time to deal with text files and get familiar with some basic techniques you can use to process them.

```python
import errno

try:
    s = open("c:/users/user/Desktop/file.txt", "rt")
    # Actual processing goes here.
    s.close()
except Exception as exc:
    if exc.errno == errno.ENOENT:
        print("The file doesn't exist.")
    elif exc.errno == errno.EMFILE:
        print("You've opened too many files.")
    else:
        print("The error number is:", exc.errno)

```
# Key takeaways

  

1. A file needs to be **open** before it can be processed by a program, and it should be **closed** when the processing is finished.

Opening the file associates it with the **stream**, which is an abstract representation of the physical data stored on the media. The way in which the stream is processed is called **open mode**. **Three** open modes exist:

-   **read mode** – only read operations are allowed;
-   **write mode** – only write operations are allowed;
-   **update mode** – both writes and reads are allowed.

  

2. Depending on the physical file content, different Python classes can be used to process files. In general, the `BufferedIOBase` is able to process any file, while `TextIOBase` is a specialized class dedicated to processing text files (i.e. files containing human-visible texts divided into lines using new-line markers). Thus, the streams can be divided into **binary** and **text** ones.

  

3. The following `open()` function syntax is used to open a file:  
  
`open(file_name, mode=open_mode, encoding=text_encoding)`  
The invocation creates a stream object and associates it with the file named `file_name`, using the specified `open_mode` and setting the specified `text_encoding`, or it **raises an exception in the case of an error**.

  

4. Three **predefined** streams are already open when the program starts:

-   `sys.stdin` – standard input;
-   `sys.stdout` – standard output;
-   `sys.stderr` – standard error output.

  

4. The `IOError` exception object, created when any file operations fails (including open operations), contains a property named `errno`, which contains the completion code of the failed action. Use this value to diagnose the problem.

  

  

**Exercise 1**

How do you encode an `open()` function’s `mode` argument value if you're going to create a new text file to only fill it with an article?

Check

`"wt"` or `"w"`

  
  

**Exercise 2**

What is the meaning of the value represented by `errno.EACESS`?

Check

**Permission denied**: you're not allowed to access the file's content.

  
  

**Exercise 3**

What is the expected output of the following code, assuming that the file named _file_ does not exist?

`import errno try: stream = open("file", "rb") print("exists") stream.close() except IOError as error: if error.errno == errno.ENOENT: print("absent") else: print("unknown")`  
Check

`absent`

# Processing text files

In this lesson we're going to prepare a simple text file with some short, simple content.

We're going to show you some basic techniques you can utilize to **read the file contents** in order to process them.

The processing will be very simple - you're going to copy the file's contents to the console, and count all the characters the program has read in.

But remember - our understanding of a text file is very strict. In our sense, it's a plain text file - it may contain only text, without any additional decorations (formatting, different fonts, etc.).

That's why you should avoid creating the file using any advanced text processor like MS Word, LibreOffice Writer, or something like this. Use the very basics your OS offers: Notepad, vim, gedit, etc.

If your text files contain some national characters not covered by the standard ASCII charset, you may need an additional step. Your `open()` function invocation may require an argument denoting specific text encoding.

For example, if you're using a Unix/Linux OS configured to use UTF-8 as a system-wide setting, the `open()` function may look as follows:

`   stream = open('file.txt', 'rt', encoding='utf-8')       `  

where the encoding argument has to be set to a value which is a string representing proper text encoding (UTF-8, here).

Consult your OS documentation to find an encoding name adequate to your environment.

  

**Note**

For the purposes of our experiments with file processing carried out in this section, we're going to use a pre-uploaded set of files (i.e., tzop.txt, or text.txt files) which you'll be able to work with. If you'd like to work with your own files locally on your machine, we strongly encourage you to do so, and to use IDLE (or any other IDE that you may prefer) to carry out your own tests.

```python
# Opening tzop.txt in read mode, returning it as a file object:
stream = open("tzop.txt", "rt", encoding = "utf-8")

print(stream.read()) # printing the content of the file


```
# Processing text files: continued

Reading a text file's contents can be performed using several different methods - none of them is any better or worse than any other. It's up to you which of them you prefer and like.

Some of them will sometimes be handier, and sometimes more troublesome. Be flexible. Don't be afraid to change your preferences.

The most basic of these methods is the one offered by the `read()` function, which you were able to see in action in the previous lesson.

If applied to a text file, the function is able to:

-   read a desired number of characters (including just one) from the file, and return them as a string;
-   read all the file contents, and return them as a string;
-   if there is nothing more to read (the virtual reading head reaches the end of the file), the function returns an empty string.

  

We'll start with the simplest variant and use a file named `text.txt`. The file has the following contents:

`Beautiful is better than ugly. Explicit is better than implicit. Simple is better than complex. Complex is better than complicated.`

**text.txt**

  

Now look at the code in the editor, and let's analyze it.

The routine is rather simple:

-   use the try-except mechanism and open the file of the predetermined name (text.txt in our case)
-   try to read the very first character from the file (`ch = s.read(1)`)
-   if you succeed (this is proven by a positive result of the `while` condition check), output the character (note the `end=` argument - it's important! You don't want to skip to a new line after every character!);
-   update the counter (`cnt`), too;
-   try to read the next character, and the process repeats.
```python
from os import strerror

try:
    cnt = 0
    s = open('text.txt', "rt")
    ch = s.read(1)
    while ch != '':
        print(ch, end='')
        cnt += 1
        ch = s.read(1)
    s.close()
    print("\n\nCharacters in file:", cnt)
except IOError as e:
    print("I/O error occurred: ", strerror(e.errno))

```
# Processing text files: continued

If you're absolutely sure that the file's length is safe and you can read the whole file to the memory at once, you can do it - the `read()` function, invoked without any arguments or with an argument that evaluates to `None`, will do the job for you.

Remember - **reading a terabyte-long file using this method may corrupt your OS**.

Don't expect miracles - computer memory isn't stretchable.

Look at the code in the editor. What do you think of it?

Let's analyze it:

-   open the file as previously;
-   read its contents by one `read()` function invocation;
-   next, process the text, iterating through it with a regular `for` loop, and updating the counter value at each turn of the loop;

The result will be exactly the same as previously.

```python
from os import strerror

try:
    cnt = 0
    s = open('text.txt', "rt")
    content = s.read()
    for ch in content:
        print(ch, end='')
        cnt += 1
    s.close()
    print("\n\nCharacters in file:", cnt)
except IOError as e:
    print("I/O error occurred: ", strerr(e.errno))

```
# Processing text files: readline()

If you want to treat the file's contents **as a set of lines**, not a bunch of characters, the `readline()` method will help you with that.

The method tries to **read a complete line of text from the file**, and returns it as a string in the case of success. Otherwise, it returns an empty string.

This opens up new opportunities - now you can also count lines easily, not only characters.

Let's make use of it. Look at the code in the editor.

As you can see, the general idea is exactly the same as in both previous examples.

```python
from os import strerror

try:
    ccnt = lcnt = 0
    s = open('text.txt', 'rt')
    line = s.readline()
    while line != '':
        lcnt += 1
        for ch in line:
            print(ch, end='')
            ccnt += 1
        line = s.readline()
    s.close()
    print("\n\nCharacters in file:", ccnt)
    print("Lines in file:     ", lcnt)
except IOError as e:
    print("I/O error occurred:", strerror(e.errno))

```
# Processing text files: readlines()

Another method, which treats text file as a set of lines, not characters, is `readlines()`.

The `readlines()` method, when invoked without arguments, tries to **read all the file contents, and returns a list of strings, one element per file line**.

If you're not sure if the file size is small enough and don't want to test the OS, you can convince the `readlines()` method to read not more than a specified number of bytes at once (the returning value remains the same - it's a list of a string).

Feel free to experiment with the following example code to understand how the `readlines()` method works:

`s = open("text.txt")`

`print(s.readlines(20))`

`print(s.readlines(20))`

`print(s.readlines(20))`

`print(s.readlines(20))`

`s.close()`

**The maximum accepted input buffer size is passed to the method as its argument**.

You may expect that `readlines()` can process a file's contents more effectively than `readline()`, as it may need to be invoked fewer times.

Note: when there is nothing to read from the file, the method returns an empty list. Use it to detect the end of the file.

To the extent of the buffer's size, you can expect that increasing it may improve input performance, but there is no golden rule for it - try to find the optimal values yourself.

  

Look at the code in the editor. We've modified it to show you how to use `readlines()`.

We've decided to use a 15-byte-long buffer. Don't think it's a recommendation.

We've used such a value to avoid the situation in which the first `readlines()` invocation consumes the whole file.

We want the method to be forced to work harder, and to demonstrate its capabilities.

There are **two nested loops in the code**: the outer one uses `readlines()`'s result to iterate through it, while the inner one prints the lines character by character.
```python
from os import strerror

try:
    ccnt = lcnt = 0
    s = open('text.txt', 'rt')
    lines = s.readlines(20)
    while len(lines) != 0:
        for line in lines:
            lcnt += 1
            for ch in line:
                print(ch, end='')
                ccnt += 1
        lines = s.readlines(10)
    s.close()
    print("\n\nCharacters in file:", ccnt)
    print("Lines in file:     ", lcnt)
except IOError as e:
    print("I/O error occurred:", strerror(e.errno))

```
# Processing text files: continued

The last example we want to present shows a very interesting trait of the object returned by the `open()` function in text mode.

We think it may surprise you - **the object is an instance of the iterable class**.

Strange? Not at all. Usable? Yes, absolutely.

The **iteration protocol defined for the file object** is very simple - its `__next__` method just **returns the next line read in from the file**.

Moreover, you can expect that the object automatically invokes `close()` when any of the file reads reaches the end of the file.

Look at the editor and see how simple and clear the code has now become.
```python
from os import strerror

try:
	ccnt = lcnt = 0
	for line in open('text.txt', 'rt'):
		lcnt += 1
		for ch in line:
			print(ch, end='')
			ccnt += 1
	print("\n\nCharacters in file:", ccnt)
	print("Lines in file:     ", lcnt)
except IOError as e:
	print("I/O error occurred: ", strerror(e.errno))

```

# Dealing with text files: write()

Writing text files seems to be simpler, as in fact there is one method that can be used to perform such a task.

The method is named `write()` and it expects just one argument - a string that will be transferred to an open file (don't forget - the open mode should reflect the way in which the data is transferred - **writing a file opened in read mode won't succeed**).

No newline character is added to the `write()`'s argument, so you have to add it yourself if you want the file to be filled with a number of lines.

The example in the editor shows a very simple code that creates a file named newtext.txt (note: the open mode `w` ensures that **the file will be created from scratch**, even if it exists and contains data) and then puts ten lines into it.

The string to be recorded consists of the word line, followed by the line number. We've decided to write the string's contents character by character (this is done by the inner `for` loop) but you're not obliged to do it in this way.

We just wanted to show you that `write()` is able to operate on single characters.

The code creates a file filled with the following text:

`line #1 line #2 line #3 line #4 line #5 line #6 line #7 line #8 line #9 line #10`

**output**

  

Can you print the file's contents to the console?

We encourage you to test the behavior of the `write()` method locally on your machine.

```python
from os import strerror

try:
	fo = open('newtext.txt', 'wt') # A new file (newtext.txt) is created.
	for i in range(10):
		s = "line #" + str(i+1) + "\n"
		for ch in s:
			fo.write(ch)
	fo.close()
except IOError as e:
	print("I/O error occurred: ", strerror(e.errno))

```

# Dealing with text files: continued

Look at the example in the editor. We've modified the previous code to write whole lines to the text file.

The contents of the newly created file are the same.

Note: you can use the same method to write to the `stderr` stream, but don't try to open it, as it's always open implicitly.

For example, if you want to send a message string to `stderr` to distinguish it from normal program output, it may look like this:

`   import sys  sys.stderr.write("Error message")   `

```python
from os import strerror

try:
    fo = open('newtext.txt', 'wt')
    for i in range(10):
        fo.write("line #" + str(i+1) + "\n")
    fo.close()
except IOError as e:
    print("I/O error occurred: ", strerror(e.errno))

```
## What is a bytearray?

Before we start talking about binary files, we have to tell you about one of the **specialized classes Python uses to store amorphous data**.

**Amorphous data is data which have no specific shape or form** - they are just a series of bytes.

This doesn't mean that these bytes cannot have their own meaning, or cannot represent any useful object, e.g., bitmap graphics.

The most important aspect of this is that in the place where we have contact with the data, we are not able to, or simply don't want to, know anything about it.

Amorphous data cannot be stored using any of the previously presented means - they are neither strings nor lists.

There should be a special container able to handle such data.

  
  

  

Python has more than one such container - one of them is **a specialized class name bytearray** - as the name suggests, it's **an array containing (amorphous) bytes**.

If you want to have such a container, e.g., in order to read in a bitmap image and process it in any way, you need to create it explicitly, using one of available constructors.

Take a look:

`   data = bytearray(10)       `  

Such an invocation creates a bytearray object able to store ten bytes.

Note: such a constructor **fills the whole array with zeros**.

# Bytearrays: continued

Bytearrays resemble lists in many respects. For example, they are **mutable**, they're a subject of the `len()` function, and you can access any of their elements using conventional indexing.

There is one important limitation - **you mustn't set any byte array elements with a value which is not an integer** (violating this rule will cause a TypeError exception) and you're **not allowed to assign a value that doesn't come from the range 0 to 255 inclusive** (unless you want to provoke a ValueError exception).

You can **treat any byte array elements as integer values** - just like in the example in the editor.

Note: we've used two methods to iterate the byte arrays, and made use of the `hex()` function to see the elements printed as hexadecimal values.

Now we're going to show you **how to write a byte array to a binary file** - binary, as we don't want to save its readable representation - we want to write a one-to-one copy of the physical memory content, byte by byte.]

```python
data = bytearray(10)

for i in range(len(data)):
    data[i] = 10 - i

for b in data:
    print(hex(b))

```

# Bytearrays: continued

So, how do we write a byte array to a binary file?

Look at the code in the editor. Let's analyze it:

-   first, we initialize `bytearray` with subsequent values starting from `10`; if you want the file's contents to be clearly readable, replace `10` with something like `ord('a')` - this will produce bytes containing values corresponding to the alphabetical part of the ASCII code (don't think it will make the file a text file - it's still binary, as it was created with a `wb` flag);
-   then, we create the file using the `open()` function - the only difference compared to the previous variants is the open mode containing the `b` flag;
-   the `write()` method takes its argument (`bytearray`) and sends it (as a whole) to the file;
-   the stream is then closed in a routine way.

The `write()` method returns a number of successfully written bytes.

If the values differ from the length of the method's arguments, it may announce some write errors.

In this case, we haven't made use of the result - this may not be appropriate in every case.

Try to run the code and analyze the contents of the newly created output file.

You're going to use it in the next step.

  

## How to read bytes from a stream

Reading from a binary file requires use of a specialized method name `readinto()`, as the method doesn't create a new byte array object, but fills a previously created one with the values taken from the binary file.

Note:

-   the method returns the number of successfully read bytes;
-   the method tries to fill the whole space available inside its argument; if there are more data in the file than space in the argument, the read operation will stop before the end of the file; otherwise, the method's result may indicate that the byte array has only been filled fragmentarily (the result will show you that, too, and the part of the array not being used by the newly read contents remains untouched)

Look at the complete code below:

`   from os import strerror  data = bytearray(10)  try:  bf = open('file.bin', 'rb')  bf.readinto(data)  bf.close()  for b in data:  print(hex(b), end=' ')  except IOError as e:  print("I/O error occurred:", strerror(e.errno))   `  

Let's analyze it:

-   first, we open the file (the one you created using the previous code) with the mode described as `rb`;
-   then, we read its contents into the byte array named `data`, of size ten bytes;
-   finally, we print the byte array contents - are they the same as you expected?

Run the code and check if it's working.
```python
from os import strerror

data = bytearray(10)

for i in range(len(data)):
    data[i] = 10 + i

try:
    bf = open('file.bin', 'wb')
    bf.write(data)
    bf.close()
except IOError as e:
    print("I/O error occurred:", strerror(e.errno))

# Your code that reads bytes from the stream should go here.

```

# How to read bytes from a stream

An alternative way of reading the contents of a binary file is offered by the method named `read()`.

Invoked without arguments, it tries to **read all the contents of the file into the memory**, making them a part of a newly created object of the bytes class.

This class has some similarities to `bytearray`, with the exception of one significant difference - it's **immutable**.

Fortunately, there are no obstacles to creating a byte array by taking its initial value directly from the bytes object, just like here:

`   from os import strerror  try:  bf = open('file.bin', 'rb')  data = bytearray(bf.read())  bf.close()  for b in data:  print(hex(b), end=' ')  except IOError as e:  print("I/O error occurred:", strerror(e.errno))   `  

Be careful - **don't use this kind of read if you're not sure that the file's contents will fit the available memory**.

```python
from os import strerror

data = bytearray(10)

for i in range(len(data)):
    data[i] = 10 + i

try:
    bf = open('file.bin', 'wb')
    bf.write(data)
    bf.close()
except IOError as e:
    print("I/O error occurred:", strerror(e.errno))

# Your code that reads bytes from the stream should go here.

```
# How to read bytes from a stream: continued

If the `read()` method is invoked with an argument, it **specifies the maximum number of bytes to be read**.

The method tries to read the desired number of bytes from the file, and the length of the returned object can be used to determine the number of bytes actually read.

You can use the method just like here:

`   try:  bf = open('file.bin', 'rb')  data = bytearray(bf.read(5))  bf.close()  for b in data:  print(hex(b), end=' ')  except IOError as e:  print("I/O error occurred:", strerror(e.errno))   `  

Note: the first five bytes of the file have been read by the code - the next five are still waiting to be processed.
```python
from os import strerror

data = bytearray(10)

for i in range(len(data)):
    data[i] = 10 + i

try:
    bf = open('file.bin', 'wb')
    bf.write(data)
    bf.close()
except IOError as e:
    print("I/O error occurred:", strerror(e.errno))

# Your code that reads bytes from the stream should go here.

```
# Copying files - a simple and functional tool

Now you're going to amalgamate all this new knowledge, add some fresh elements to it, and use it to write a real code which is able to actually copy a file's contents.

Of course, the purpose is not to make a better replacement for commands like _copy_ (MS Windows) or _cp_ (Unix/Linux) but to see one possible way of creating a working tool, even if nobody wants to use it.

Look at the code in the editor. Let's analyze it:

-   lines 3 through 8: ask the user for the name of the file to copy, and try to open it to read; terminate the program execution if the open fails; note: use the `exit()` function to stop program execution and to pass the completion code to the OS; any completion code other than `0` says that the program has encountered some problems; use the `errno` value to specify the nature of the issue;
-   lines 10 through 16: repeat nearly the same action, but this time for the output file;
-   line 18: prepare a piece of memory for transferring data from the source file to the target one; such a transfer area is often called a buffer, hence the name of the variable; the size of the buffer is arbitrary - in this case, we decided to use 64 kilobytes; technically, a larger buffer is faster at copying items, as a larger buffer means fewer I/O operations; actually, there is always a limit, the crossing of which renders no further improvements; test it yourself if you want.
-   line 19: count the bytes copied - this is the counter and its initial value;
-   line 21: try to fill the buffer for the very first time;
-   line 22: as long as you get a non-zero number of bytes, repeat the same actions;
-   line 23: write the buffer's contents to the output file (note: we've used a slice to limit the number of bytes being written, as `write()` always prefer to write the whole buffer)
-   line 24: update the counter;
-   line 25: read the next file chunk;
-   lines 30 through 32: some final cleaning - the job is done.
```python
from os import strerror

srcname = input("Enter the source file name: ")
try:
    src = open(srcname, 'rb')
except IOError as e:
    print("Cannot open the source file: ", strerror(e.errno))
    exit(e.errno)	

dstname = input("Enter the destination file name: ")
try:
    dst = open(dstname, 'wb')
except Exception as e:
    print("Cannot create the destination file: ", strerror(e.errno))
    src.close()
    exit(e.errno)	

buffer = bytearray(65536)
total  = 0
try:
    readin = src.readinto(buffer)
    while readin > 0:
        written = dst.write(buffer[:readin])
        total += written
        readin = src.readinto(buffer)
except IOError as e:
    print("Cannot create the destination file: ", strerror(e.errno))
    exit(e.errno)	
    
print(total,'byte(s) succesfully written')
src.close()
dst.close()

```

##   
Estimated time

30-60 minutes

## Level of difficulty

Medium

## Objectives

-   improving the student's skills in operating with files (reading)
-   using data collections for counting numerous data.

## Scenario

A text file contains some text (nothing unusual) but we need to know how often (or how rare) each letter appears in the text. Such an analysis may be useful in cryptography, so we want to be able to do that in reference to the Latin alphabet.

Your task is to write a program which:

-   asks the user for the input file's name;
-   reads the file (if possible) and counts all the Latin letters (lower- and upper-case letters are treated as equal)
-   prints a simple histogram in alphabetical order (only non-zero counts should be presented)

Create a test file for the code, and check if your histogram contains valid results.

Assuming that the test file contains just one line filled with:

`aBc`

**samplefile.txt**

the expected output should look as follows:

`a -> 1 b -> 1 c -> 1`

**output**

**Tip**: We think that a dictionary is a perfect data collection medium for storing the counts. The letters may be keys while the counters can be values.
## stimated time

15-30 minutes

## Level of difficulty

Medium

## Prerequisites

4.3.1.15

## Objectives

-   improve the student's skills in operating with files (reading/writing)
-   using lambdas to change the sort order.

## Scenario

The previous code needs to be improved. It's okay, but it has to be better.

Your task is to make some amendments, which generate the following results:

-   the output histogram will be sorted based on the characters' frequency (the bigger counter should be presented first)
-   the histogram should be sent to a file with the same name as the input one, but with the suffix '.hist' (it should be concatenated to the original name)

Assuming that the input file contains just one line filled with:

`cBabAa`

**samplefile.txt**

the expected output should look as follows:

`a -> 3 b -> 2 c -> 1`

**output**

**Tip**: Use a `lambda` to change the sort order.

## Estimated time

30-90 minutes

## Level of difficulty

Medium

## Objectives

-   improve the student's skills in operating with files (reading)
-   perfecting the student's abilities in defining and using self-defined exceptions and dictionaries.

## Scenario

Prof. Jekyll conducts classes with students and regularly makes notes in a text file. Each line of the file contains three elements: the student's first name, the student's last name, and the number of point the student received during certain classes.

The elements are separated with white spaces. Each student may appear more than once inside Prof. Jekyll's file.

The file may look as follows:

`John Smith 5 Anna Boleyn 4.5 John Smith 2 Anna Boleyn 11 Andrew Cox 1.5`

**samplefile.txt**

Your task is to write a program which:

-   asks the user for Prof. Jekyll's file name;
-   reads the file contents and counts the sum of the received points for each student;
-   prints a simple (but sorted) report, just like this one:

`Andrew Cox 1.5 Anna Boleyn 15.5 John Smith 7.0`

**output**

Note:

-   your program must be fully protected against all possible failures: the file's non-existence, the file's emptiness, or any input data failures; encountering any data error should cause immediate program termination, and the erroneous should be presented to the user;
-   implement and use your own exceptions hierarchy - we've presented it in the editor; the second exception should be raised when a bad line is detect, and the third when the source file exists but is empty.

**Tip**: Use a dictionary to store the students' data.

```python
class StudentsDataException(Exception):
    pass


class BadLine(StudentsDataException):
    # Write your code here.


class FileEmpty(StudentsDataException):
    # Write your code here.

```
# Key takeaways

  

1. To read a file’s contents, the following stream methods can be used:

-   `read(number)` – reads the `number` characters/bytes from the file and returns them as a string; is able to read the whole file at once;
-   `readline()` – reads a single line from the text file;
-   `readlines(number)` – reads the `number` lines from the text file; is able to read all lines at once;
-   `readinto(bytearray)` – reads the bytes from the file and fills the `bytearray` with them;

  

2. To write new content into a file, the following stream methods can be used:

-   `write(string)` – writes a `string` to a text file;
-   `write(bytearray)` – writes all the bytes of `bytearray` to a file;

  

3. The `open()` method returns an iterable object which can be used to iterate through all the file's lines inside a `for` loop. For example:

`   for line in open("file", "rt"):  print(line, end='')   `  

The code copies the file's contents to the console, line by line. **Note**: the stream closes itself **automatically** when it reaches the end of the file.

  

**Exercise 1**

What do we expect from the `readlines()` method when the stream is associated with an empty file?

Check  
  

**Exercise 2**

What is the following code intended to do?

`for line in open("file", "rt"): for char in line: if char.lower() not in "aeiouy ": print(char, end='')`  
Check

It copies the _file_'s contents to the console, ignoring all vowels.

  
  

**Exercise 3**

You're going to process a bitmap stored in a file named `image.png`, and you want to read its contents as a whole into a _bytearray_ variable named `image`. Add a line to the following code to achieve this goal.

`try: stream = open("image.png", "rb") # Insert a line here. stream.close() except IOError: print("failed") else: print("success")`  
Check

`image = bytearray(stream.read())`

# Introduction to the os module

In this section, you'll learn about a module called _os_, which lets you **interact with the operating system using Python**.

It provides functions that are available on Unix and/or Windows systems. If you're familiar with the command console, you'll see that some functions give the same results as the commands available on the operating systems.

A good example of this is the `mkdir` function, which allows you to create a directory just like the _mkdir_ command in Unix and Windows. If you don't know this command, don't worry.

You'll soon have the opportunity to learn the functions of the _os_ module, to perform operations on files and directories along with the corresponding commands.

In addition to file and directory operations, the _os_ module enables you to:

-   get information about the operating system;
-   manage processes;
-   operate on I/O streams using file descriptors.
![[Pasted image 20221224134204.png]]
  
In a moment, you'll see how to get basic information about your operating system, although process management and working with file descriptors won't be discussed here, because these are more advanced topics that require knowledge of operating system mechanisms.

Ready?

# Getting information about the operating system

Before you create your first directory structure, you'll see how you can get information about the current operating system. This is really easy because the _os_ module provides a function called _uname_, which returns an object containing the following attributes:

-   **systemname** — stores the name of the operating system;
-   **nodename** — stores the machine name on the network;
-   **release** — stores the operating system release;
-   **version** — stores the operating system version;
-   **machine** — stores the hardware identifier, e.g., x86_64.

Let's look at how it is in practice:

`import os`

`print(os.uname())`

Result:

`posix.uname_result(sysname='Linux', nodename='192d19f04766', release='4.4.0-164-generic', version='#192-Ubuntu SMP Fri Sep 13 12:02:50 UTC 2019', machine='x86_64')`

**output**

As you can see, the _uname_ function returns an object containing information about the operating system. The above code was launched on Ubuntu 16.04.6 LTS, so don't be surprised if you get a different result, because it depends on your operating system.

Unfortunately, the _uname_ function only works on some Unix systems. If you use Windows, you can use the _uname_ function in the _platform_ module, which returns a similar result.

The _os_ module allows you to quickly distinguish the operating system using the _name_ attribute, which supports one of the following names:

-   **posix** — you'll get this name if you use Unix;
-   **nt** — you'll get this name if you use Windows;
-   **java** — you'll get this name if your code is written in Jython.

For Ubuntu 16.04.6 LTS, the _name_ attribute returns the name _posix_:

`import os`

`print(os.name)`

Result:

`posix`

**output**

**NOTE:** On Unix systems, there's a command called _uname_ that returns the same information (if you run it with the -a option) as the _uname_ function.
# Creating directories in Python

The _os_ module provides a function called _mkdir_, which, like the _mkdir_ command in Unix and Windows, allows you to create a directory. The _mkdir_ function requires a path that can be relative or absolute. Let's recall what both paths look like in practice:

-   **my_first_directory** — this is a relative path which will create the _my_first_directory_ directory in the current working directory;
-   **./my_first_directory** — this is a relative path that explicitly points to the current working directory. It has the same effect as the path above;
-   **../my_first_directory** — this is a relative path that will create the _my_first_directory_ directory in the parent directory of the current working directory;
-   **/python/my_first_directory** — this is the absolute path that will create the _my_first_directory_ directory, which in turn is in the _python_ directory in the root directory.

Look at the code in the editor. It shows an example of how to create the _my_first_directory_ directory using a relative path. This is the simplest variant of the relative path, which consists of passing only the directory name.

If you test your code here, it will output the newly created `['my_first_directory']` directory (and the entire content of the current working catalog).

The _mkdir_ function creates a directory in the specified path. Note that running the program twice will raise a _FileExistsError_.

This means that we cannot create a directory if it already exists. In addition to the path argument, the _mkdir_ function can optionally take the _mode_ argument, which specifies directory permissions. However, on some systems, the _mode_ argument is ignored.

To change the directory permissions, we recommend the _chmod_ function, which works similarly to the _chmod_ command on Unix systems. You can find more information about it in the documentation.

In the above example, another function provided by the _os_ module named _listdir_ is used. The _listdir_ function returns a list containing the names of the files and directories that are in the path passed as an argument.

If no argument is passed to it, the current working directory will be used (as in the example above). It's important that the result of the _listdir_ function omits the entries '.' and '..', which are displayed, e.g., when using the _ls -a_ command on Unix systems.

**NOTE:** In both Windows and Unix, there's a command called _mkdir_, which requires a directory path. The equivalent of the above code that creates the _my_first_directory_ directory is the _mkdir my_first_directory_ command.

```python
import os

os.mkdir("my_first_directory")
print(os.listdir())

```
# Recursive directory creation

The `mkdir` function is very useful, but what if you need to create another directory in the directory you've just created. Of course, you can go to the created directory and create another directory inside it, but fortunately the _os_ module provides a function called `makedirs`, which makes this task easier.

The _makedirs_ function enables recursive directory creation, which means that all directories in the path will be created. Let's look at the code in the editor and see how it is in practice.

The code should produce the following result:

`['my_second_directory']`

**output**

The code creates two directories. The first of them is created in the current working directory, while the second in the _my_first_directory_ directory.

You don't have to go to the _my_first_directory_ directory to create the _my_second_directory_ directory, because the _makedirs_ function does this for you. In the example above, we go to the _my_first_directory_ directory to show that the _makedirs_ command creates the _my_second_directory_ subdirectory.

To move between directories, you can use a function called _chdir_, which changes the current working directory to the specified path. As an argument, it takes any relative or absolute path. In our example, we pass the first directory name to it.

**NOTE:** The equivalent of the _makedirs_ function on Unix systems is the _mkdir_ command with the _-p_ flag, while in Windows, simply the _mkdir_ command with the path:

-   Unix-like systems:  
      
    `mkdir -p my_first_directory/my_second_directory`
  
-   Windows:  
      
    `mkdir my_first_directory/my_second_directory`
```python
import os

os.makedirs("my_first_directory/my_second_directory")
os.chdir("my_first_directory")
print(os.listdir())

```
# Where am I now?

You already know how to create directories and how to move between them. Sometimes, when you have a really large directory structure that you navigate, you may not know which directory you're currently working in.
![[Pasted image 20221224134306.png]]
As you’ve probably guessed, the _os_ module provides a function that returns information about the current working directory. It's called `getcwd`. Look at the code in the editor to see how to use it in practice.

Result:

`.../my_first_directory .../my_first_directory/my_second_directory`

**output**

In the example, we create the _my_first_directory_ directory, and the _my_second_directory_ directory inside it. In the next step, we change the current working directory to the _my_first_directory_ directory, and then display the current working directory (first line of the result).

Next, we go to the _my_second_directory_ directory and again display the current working directory (second line of the result). As you can see, the _getcwd_ function returns the absolute path to the directories.

**NOTE:** On Unix-like systems, the equivalent of the _getcwd_ function is the _pwd_ command, which prints the name of the current working directory.
```python
import os

os.makedirs("my_first_directory/my_second_directory")
os.chdir("my_first_directory")
print(os.getcwd())
os.chdir("my_second_directory")
print(os.getcwd())

```

# Deleting directories in Python

The _os_ module also allows you to delete directories. It gives you the option of deleting a single directory or a directory with its subdirectories. To delete a single directory, you can use a function called `rmdir`, which takes the path as its argument. Look at the code in the editor.

The above example is really simple. First, the _my_first_directory_ directory is created, and then it's removed using the _rmdir_ function. The _listdir_ function is used as proof that the directory has been removed successfully. In this case, it returns an empty list. When deleting a directory, make sure it exists and is empty, otherwise an exception will be raised.

To remove a directory and its subdirectories, you can use the `removedirs` function, which requires you to specify a path containing all directories that should be removed:

`import os`

`os.makedirs("my_first_directory/my_second_directory")`

`os.removedirs("my_first_directory/my_second_directory")`

`print(os.listdir())`

As with the _rmdir_ function, if one of the directories doesn't exist or isn't empty, an exception will be raised.

**NOTE:** In both Windows and Unix, there's a command called _rmdir_, which, just like the _rmdir_ function, removes directories. What's more, both systems have commands to delete a directory and its contents. In Unix, this is the _rm_ command with the _-r_ flag.
```python
import os

os.mkdir("my_first_directory")
print(os.listdir())
os.rmdir("my_first_directory")
print(os.listdir())

```
# The system() function

All functions presented in this part of the course can be replaced by a function called _system_, which executes a command passed to it as a string.

The `system` function is available in both Windows and Unix. Depending on the system, it returns a different result.

In Windows, it returns the value returned by the shell after running the command given, while in Unix, it returns the exit status of the process.

Let's look at the code in the editor and see how it is in practice.

Result:

`0`

**output**

The above example will work in both Windows and Unix. In our case, we receive exit status 0, which indicates success on Unix systems.

This means that the _my_first_directory_ directory has been created. As part of the exercise, try to list the contents of the directory where you created the _my_first_directory_ directory.

```python
import os

returned_value = os.system("mkdir my_first_directory")
print(returned_value)

```
**LAB**  
  

## Estimated time

15-30 min

## Level of difficulty

Easy

## Objectives

-   improving the student's skills in interacting with the operating system;
-   practical use of known functions provided by the _os_ module.

## Scenario

It goes without saying that operating systems allow you to search for files and directories. While studying this part of the course, you learned about the functions of the _os_ module, which have everything you need to write a program that will search for directories in a given location.

To make your task easier, we have prepared a test directory structure for you:

  

![[Pasted image 20221224134355.png]]

  
  

Your program should meet the following requirements:

1.  Write a function or method called _find_ that takes two arguments called _path_ and _dir_. The _path_ argument should accept a relative or absolute path to a directory where the search should start, while the _dir_ argument should be the name of a directory that you want to find in the given path. Your program should display the absolute paths if it finds a directory with the given name.
2.  The directory search should be done recursively. This means that the search should also include all subdirectories in the given path.

**Example input:**

`path="./tree", dir="python"`  

**Example output:**

`.../tree/python .../tree/cpp/other_courses/python .../tree/c/other_courses/python`

# Key takeaways

1. The `uname` function returns an object that contains information about the current operating system. The object has the following attributes:

-   _systemname_ (stores the name of the operating system)
-   _nodename_ (stores the machine name on the network)
-   _release_ (stores the operating system release)
-   _version_ (stores the operating system version)
-   _machine_ (stores the hardware identifier, e.g. x86_64.)

2. The _name_ attribute available in the `os` module allows you to distinguish the operating system. It returns one of the following three values:

-   _posix_ (you'll get this name if you use Unix)
-   _nt_ (you'll get this name if you use Windows)
-   _java_ (you'll get this name if your code is written in something like Jython)

3. The `mkdir` function creates a directory in the path passed as its argument. The path can be either relative or absolute, e.g:

`   import os  os.mkdir("hello") # the relative path  os.mkdir("/home/python/hello") # the absolute path   `  

**Note**: If the directory exists, a `FileExistsError` exception will be thrown. In addition to the `mkdir` function, the `os` module provides the `makedirs` function, which allows you to recursively create all directories in a path.

4. The result of the `listdir()` function is a list containing the names of the files and directories that are in the path passed as its argument.

It's important to remember that the `listdir` function omits the entries '.' and '..', which are displayed, for example, when using the `ls -a` command on Unix systems. If the path isn't passed, the result will be returned for the current working directory.

5. To move between directories, you can use a function called `chdir()`, which changes the current working directory to the specified path. As its argument, it takes any relative or absolute path.

If you want to find out what the current working directory is, you can use the `getcwd()` function, which returns the path to it.

6. To remove a directory, you can use the `rmdir()` function, but to remove a directory and its subdirectories, use the `removedirs()` function.

7. On both Unix and Windows, you can use the system function, which executes a command passed to it as a string, e.g.:

`   import os  returned_value = os.system("mkdir hello")   `  

The system function on Windows returns the value returned by shell after running the command given, while on Unix it returns the exit status of the process.

  
  

  

**Exercise 1**

What is the output of the following snippet if you run it on Unix?

`import os print(os.name)`

Check

`posix`

  
  

**Exercise 2**

What is the output of the following snippet?

`import os os.mkdir("hello") print(os.listdir())`

Check

`['hello']`

# Introduction to the datetime module

In this section, you'll learn about a Python module called _datetime_.

As you can guess, it provides **classes for working with date and time**. If you think you don't need to delve into this topic, let's talk about examples of using date and time in programming.

Date and time have countless uses and it's probably hard to find a production application that doesn't use them. Here are some examples:

-   **event logging** — thanks to the knowledge of date and time, we are able to determine when exactly a critical error occurs in our application. When creating logs, you can specify the date and time format;
-   **tracking changes in the database** — sometimes it's necessary to store information about when a record was created or modified. The _datetime_ module will be perfect for this case;
-   **data validation** — you'll soon learn how to read the current date and time in Python. Knowing the current date and time, we're able to validate various types of data, e.g., whether a discount coupon entered by a user in our application is still valid;
-   **storing important information** — can you imagine bank transfers without storing the information of when they were made? The date and time of certain actions must be preserved, and we must deal with it.
![[Pasted image 20221224134427.png]]
# Getting the current local date and creating date objects

One of the classes provided by the `datetime` module is a class called `date`. Objects of this class represent a date consisting of the year, month, and day. Look at the code in the editor to see what it looks like in practice and get the current local date using the `today` method.

Run the code to see what happens.

The `today` method returns a `date` object representing the current local date. Note that the `date` object has three attributes: _year_, _month_, and _day_.

Be careful, because these attributes are read-only. To create a `date` object, you must pass the _year_, _month_, and _day_ parameters as follows:

`from datetime import date`

`my_date = date(2019, 11, 4)`

`print(my_date)`

Run the example to see what happens.

When creating a _date_ object, keep the following restrictions in mind:
![[Pasted image 20221224134441.png]]
**Note:** Later in this course you'll learn how to change the default date format.
```python
from datetime import date

today = date.today()

print("Today:", today)
print("Year:", today.year)
print("Month:", today.month)
print("Day:", today.day)

```
# Creating a date object from a timestamp

The `date` class gives us the ability to create a _date_ object from a _timestamp_.

In Unix, the timestamp expresses the number of seconds since January 1, 1970, 00:00:00 (UTC). This date is called the **Unix epoch**, because this is when the counting of time began on Unix systems.

The timestamp is actually the difference between a particular date (including time) and January 1, 1970, 00:00:00 (UTC), expressed in seconds.

To create a date object from a timestamp, we must pass a Unix timestamp to the `fromtimestamp` method.

For this purpose, we can use the `time` module, which provides time-related functions. One of them is a function called `time()` that returns the number of seconds from January 1, 1970 to the current moment in the form of a float number. Take a look at the example in the editor.

Run the code to see the output.

If you run the sample code several times, you'll be able to see how the timestamp increments itself. It's worth adding that the result of the `time` function depends on the platform, because **in Unix and Windows systems, leap seconds aren't counted**.

**Note:** In this part of the course we'll also talk about the _time_ module.
```python
from datetime import date
import time

timestamp = time.time()
print("Timestamp:", timestamp)

d = date.fromtimestamp(timestamp)
print("Date:", d)

```
# Creating a date object using the ISO format

The `datetime` module provides several methods to create a `date` object. One of them is the `fromisoformat` method, which takes a date in the **YYYY-MM-DD** format compliant with the ISO 8601 standard.

The ISO 8601 standard defines how the date and time are represented. It's often used, so it's worth taking a moment to familiarize yourself with it. Take a look at the picture describing the values required by the format:
![[Pasted image 20221224134510.png]]
Now look at the code in the editor and run it.

In our example, YYYY is 2019, MM is 11 (November), and DD is 04 (fourth day of November).

When substituting the date, be sure to add 0 before a month or a day that is expressed by a number less than 10.

**Note:** The `fromisoformat` method has been available in Python since version 3.7.
```python
from datetime import date

d = date.fromisoformat('2019-11-04')
print(d)

```
# The replace() method

Sometimes you may need to replace the year, month, or day with a different value. You can’t do this with the year, month, and day attributes because they're read-only. In this case, you can use the method named `replace`.

Run the code in the editor.

Result:

`1991-02-05 1992-01-16`

**output**

The _year_, _month_, and _day_ parameters are optional. You can pass only one parameter to the `replace` method, e.g., _year_, or all three as in the example.

The `replace` method returns a changed _date_ object, so you must remember to assign it to some variable.

```python
from datetime import date

d = date(1991, 2, 5)
print(d)

d = d.replace(year=1992, month=1, day=16)
print(d)

```
# What day of the week is it?

One of the more helpful methods that makes working with dates easier is the method called `weekday`. It returns the day of the week as an integer, where 0 is Monday and 6 is Sunday. Run the code in the editor.

Result:

`0`

**output**

![[Pasted image 20221224134547.png]]
The `date` class has a similar method called `isoweekday`, which also returns the day of the week as an integer, but 1 is Monday, and 7 is Sunday:

`from datetime import date`

`d = date(2019, 11, 4)`

`print(d.isoweekday())`

Result:

`1`

**output**

As you can see, for the same date we get a different integer, but expressing the same day of the week. The integer returned by the `isodayweek` method follows the ISO 85601 specification.

```python
from datetime import date

d = date(2019, 11, 4)
print(d.weekday())

```
# Creating time objects

You already know how to present a date using the `date` object. The `datetime` module also has a class that allows you to present time. Can you guess its name? Yes, it's called `time`:

`time(hour, minute, second, microsecond, _tzinfo, fold_)`

The `time` class constructor accepts the following optional parameters:

![[Pasted image 20221224134708.png]]
The _tzinfo_ parameter is associated with time zones, while _fold_ with wall times. We won't use them during this course, but we encourage you to familiarize yourself with them.

Let's look at how to create a time object in practice. Run the code in the editor.

Result:

`Time: 14:53:20.000001 Hour: 14 Minute: 53 Second: 20 Microsecond: 1`

**output**

In the example, we passed four parameters to the class constructor: _hour_, _minute_, _second_, and _microsecond_. Each of them can be accessed using the class attributes.

**Note:** Soon we'll tell you how you can change the default time formatting.
```python
from datetime import time

t = time(14, 53, 20, 1)

print("Time:", t)
print("Hour:", t.hour)
print("Minute:", t.minute)
print("Second:", t.second)
print("Microsecond:", t.microsecond)

```
# The time module

In addition to the `time` class, the Python standard library offers a module called `time`, which provides a time-related function. You already had the opportunity to learn the function called `time` when discussing the `date` class. Now we'll look at another useful function available in this module.

You must spend many hours in front of a computer while doing this course. Sometimes you may feel the need to take a nap. Why not? Let's write a program that simulates a student's short nap. Have a look at the code in the editor.

Result:

`I'm very tired. I have to take a nap. See you later. I slept well! I feel great!`

**output**

The most important part of the sample code is the use of the `sleep` function (yes, you may remember it from one of the previous labs earlier in the course), which suspends program execution for the given number of seconds.

In our example it's 5 seconds. You're right, it's a very short nap.

Extend the student's sleep by changing the number of seconds. Note that the `sleep` function accepts only an integer or a floating point number.

```python
import time

class Student:
    def take_nap(self, seconds):
        print("I'm very tired. I have to take a nap. See you later.")
        time.sleep(seconds)
        print("I slept well! I feel great!")

student = Student()
student.take_nap(5)

```

# The ctime() function

The `time` module provides a function called `ctime`, which **converts the time in seconds since January 1, 1970 (Unix epoch) to a string**.

Do you remember the result of the `time` function? That's what you need to pass to `ctime`. Take a look at the example in the editor.

Result:

`Mon Nov 4 14:53:00 2019`

**output**

The `ctime` function returns a string for the passed timestamp. In our example, the timestamp expresses November 4, 2019 at 14:53:00.

It's also possible to call the `ctime` function without specifying the time in seconds. In this case, the current time will be returned:

`import time`

`print(time.ctime())`

```python
import time

timestamp = 1572879180
print(time.ctime(timestamp))

```
# The gmtime() and localtime() functions

Some of the functions available in the `time` module require knowledge of the _struct_time_ class, but before we get to know them, let's see what the class looks like:

`time.struct_time:`

`tm_year # specifies the year`

`tm_mon # specifies the month (value from 1 to 12)`

`tm_mday # specifies the day of the month (value from 1 to 31)`

`tm_hour # specifies the hour (value from 0 to 23)`

`tm_min # specifies the minute (value from 0 to 59)`

`tm_sec # specifies the second (value from 0 to 61 )`

`tm_wday # specifies the weekday (value from 0 to 6)`

`tm_yday # specifies the year day (value from 1 to 366)`

`tm_isdst # specifies whether daylight saving time applies (1 – yes, 0 – no, -1 – it isn't known)`

`tm_zone # specifies the timezone name (value in an abbreviated form)`

`tm_gmtoff # specifies the offset east of UTC (value in seconds)`

The _struct_time_ class also allows access to values using indexes. Index `0` returns the value in _tm_year_, while `8` returns the value in _tm_isdst_.

The exceptions are _tm_zone_ and _tm_gmoff_, which cannot be accessed using indexes. Let's look at how to use the _struct_time_ class in practice. Run the code in the editor.

Result:

`time.struct_time(tm_year=2019, tm_mon=11, tm_mday=4, tm_hour=14, tm_min=53, tm_sec=0, tm_wday=0, tm_yday=308, tm_isdst=0) time.struct_time(tm_year=2019, tm_mon=11, tm_mday=4, tm_hour=14, tm_min=53, tm_sec=0, tm_wday=0, tm_yday=308, tm_isdst=0)`

**output**

The example shows two functions that convert the elapsed time from the Unix epoch to the _struct_time_ object. The difference between them is that the `gmtime` function returns the _struct_time_ object in UTC, while the `localtime` function returns local time. For the `gmtime` function, the _tm_isdst_ attribute is always 0.

```python
import time

timestamp = 1572879180
print(time.gmtime(timestamp))
print(time.localtime(timestamp))

```
# The asctime() and mktime() functions

The `time` module has functions that expect a _struct_time_ object or a tuple that stores values according to the indexes presented when discussing the _struct_time_ class. Run the example in the editor.

Result:

`Mon Nov 4 14:53:00 2019 1572879180.0`

**output**

The first of the functions, called `asctime`, converts a _struct_time_ object or a tuple to a string. Note that the familiar `gmtime` function is used to get the _struct_time_ object. If you don't provide an argument to the `asctime` function, the time returned by the `localtime` function will be used.

The second function called `mktime` converts a _struct_time_ object or a tuple that expresses the local time to the number of seconds since the Unix epoch. In our example, we passed a tuple to it, which consists of the following values:

2019 => tm_year  
11 => tm_mon  
4 => tm_mday  
14 => tm_hour  
53 => tm_min  
0 => tm_sec  
0 => tm_wday  
308 => tm_yday  
0 => tm_isdst

```python
import time

timestamp = 1572879180
st = time.gmtime(timestamp)

print(time.asctime(st))
print(time.mktime((2019, 11, 4, 14, 53, 0, 0, 308, 0)))

```
# Creating datetime objects

In the `datetime` module, date and time can be represented as separate objects or as one. The class that combines date and time is called `datetime`.

`datetime(year, month, day, hour, minute, second, microsecond, _tzinfo, fold_)`

Its constructor accepts the following parameters:

![[Pasted image 20221224135214.png]]
Now let's have a look at the code in the editor to see how we create a datetime object.

Result:

`Datetime: 2019-11-04 14:53:00 Date: 2019-11-04 Time: 14:53:00`

**output**

The example creates a `datetime` object representing November 4, 2019 at 14:53:00. All parameters passed to the constructor go to read-only class attributes. They're _year_, _month_, _day_, _hour_, _minute_, _second_, _microsecond_, _tzinfo_, and _fold_.

The example shows two methods that return two different objects. The method called `date` returns the _date_ object with the given year, month, and day, while the method called `time` returns the _time_ object with the given hour and minute.
```python
from datetime import datetime

dt = datetime(2019, 11, 4, 14, 53)

print("Datetime:", dt)
print("Date:", dt.date())
print("Time:", dt.time())

```
# Methods that return the current date and time

The `datetime` class has several methods that return the current date and time. These methods are:

-   `today()` — returns the current local date and time with the _tzinfo_ attribute set to _None_;
-   `now()` — returns the current local date and time the same as the _today_ method, unless we pass the optional argument _tz_ to it. The argument of this method must be an object of the _tzinfo_ subclass;
-   `utcnow()` — returns the current UTC date and time with the _tzinfo_ attribute set to _None_.

Run the code in the editor to see them all in practice. What can you say about the output?

As you can see, the result of all the three methods is the same. The small differences are caused by the time elapsed between subsequent calls.

**Note:** You can read more about _tzinfo_ objects in the documentation.
```python
from datetime import datetime

print("today:", datetime.today())
print("now:", datetime.now())
print("utcnow:", datetime.utcnow())

```
# Getting a timestamp

There are many converters available on the Internet that can calculate a timestamp based on a given date and time, but how can we do it in the `datetime` module?

This is possible thanks to the `timestamp` method provided by the `datetime` class. Look at the code in the editor.

Result:

`Timestamp: 1601823300.0`

**output**

The `timestamp` method returns a float value expressing the number of seconds elapsed between the date and time indicated by the _datetime_ object and January 1, 1970, 00:00:00 (UTC).
```python
from datetime import datetime

dt = datetime(2020, 10, 4, 14, 55)
print("Timestamp:", dt.timestamp())

```
# Date and time formatting (part 1)

All `datetime` module classes presented so far have a method called `strftime`. This is a very important method, because it allows us to return the date and time in the format we specify.

The `strftime` method takes only one argument in the form of a string specifying the format that can consist of directives.

A directive is a string consisting of the character `%` (percent) and a lowercase or uppercase letter, e.g., the directive `%Y` means the year with the century as a decimal number. Let's see it in an example. Run the code in the editor.

Result:

`2020/01/04`

**output**

In the example, we passed a format consisting of three directives separated by `/` (slash) to the `strftime` method. Of course, the separator character can be replaced by another character, or even by a string.

You can put any characters in the format, but only recognizable directives will be replaced with the appropriate values. In our format we've used the following directives:

-   `%Y` – returns the year with the century as a decimal number. In our example, this is 2020.
-   `%m` – returns the month as a zero-padded decimal number. In our example, it's 01.
-   `%d` – returns the day as a zero-padded decimal number. In our example, it's 04.

**Note:** You can find all available directives [here](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes).

```python
from datetime import date

d = date(2020, 1, 4)
print(d.strftime('%Y/%m/%d'))

```
# Date and time formatting (part 2)

Time formatting works in the same way as date formatting, but requires the use of appropriate directives. Let's take a closer look at a few of them in the editor.

Result:

`14:53:00 20/November/04 14:53:00`

**output**

The first of the formats used concerns only time. As you can guess, `%H` returns the hour as a zero-padded decimal number, `%M` returns the minute as a zero-padded decimal number, while `%S` returns the second as a zero-padded decimal number. In our example, `%H` is replaced by 14, `%M` by 53, and `%S` by 00.

The second format used combines date and time directives. There are two new directives, `%Y` and `%B`. The directive `%Y` returns the year without a century as a zero-padded decimal number (in our example it's 20). The `%B` directive returns the month as the locale’s full name (in our example, it's November).

In general, you've got a lot of freedom in creating formats, but you must remember to use the directives properly. As an exercise, you can check what happens if, for example, you try to use the `%Y` directive in the format passed to the time object's _strftime_ method. Try to find out why you got this result yourself. Good luck!

```python
from datetime import time
from datetime import datetime

t = time(14, 53)
print(t.strftime("%H:%M:%S"))

dt = datetime(2020, 11, 4, 14, 53)
print(dt.strftime("%y/%B/%d %H:%M:%S"))

```
# The strftime() function in the time module

You probably won't be surprised to learn that the `strftime` function is available in the `time` module. It differs slightly from the `strftime` methods in the classes provided by the `datetime` module because, in addition to the format argument, it can also take (optionally) a tuple or struct_time object.

If you don't pass a tuple or _struct_time_ object, the formatting will be done using the current local time. Take a look at the example in the editor.

Our result looks as follows:

`2019/11/04 14:53:00 2020/10/12 12:19:40`

**sample output**

Creating a format looks the same as for the `strftime` methods in the `datetime` module. In our example, we use the `%Y`, `%m`, `%d`, `%H`, `%M`, and `%S` directives that you already know.

In the first function call, we format the _struct_time_ object, while in the second call (without the optional argument), we format the local time. You can find all available directives in the `time` module [here](https://docs.python.org/3/library/time.html#time.strftime).

```python
import time

timestamp = 1572879180
st = time.gmtime(timestamp)

print(time.strftime("%Y/%m/%d %H:%M:%S", st))
print(time.strftime("%Y/%m/%d %H:%M:%S"))

```
# The strptime() method

Knowing how to create a format can be helpful when using a method called `strptime` in the `datetime` class. Unlike the `strftime` method, it creates a `datetime` object from a string representing a date and time.

The `strptime` method requires you to specify the format in which you saved the date and time. Let's see it in an example. Take a look at the code in the editor.

Result:

`2019-11-04 14:53:00`

**output**

In the example, we've specified two required arguments. The first is a date and time as a string: `"2019/11/04 14:53:00"`, while the second is a format that facilitates parsing to a `datetime` object. Be careful, because if the format you specify doesn't match the date and time in the string, it'll raise a _ValueError_.

**Note:** In the `time` module, you can find a function called `strptime`, which parses a string representing a time to a _struct_time_ object. Its use is analogous to the `strptime` method in the `datetime` class:

`import time`

`print(time.strptime("2019/11/04 14:53:00", "%Y/%m/%d %H:%M:%S"))`

Its result will be as follows:

`time.struct_time(tm_year=2019, tm_mon=11, tm_mday=4, tm_hour=14, tm_min=53, tm_sec=0, tm_wday=0, tm_yday=308, tm_isdst=-1)`

**output**

```python
from datetime import datetime
print(datetime.strptime("2019/11/04 14:53:00", "%Y/%m/%d %H:%M:%S"))

```
# Date and time operations

Sooner or later you'll have to perform some calculations on the date and time. Fortunately, there's a class called `timedelta` in the `datetime` module that was created for just such a purpose.

To create a `timedelta` object, just do subtraction on the `date` or `datetime` objects, just like we did in the example in the editor. Run it.

Result:

`366 days, 0:00:00 365 days, 9:07:00`

**output**

The example shows subtraction for both the `date` and `datetime` objects. In the first case, we receive the difference in days, which is 366 days. Note that the difference in hours, minutes, and seconds is also displayed. In the second case, we receive a different result, because we specified the time that was included in the calculations. As a result, we receive 365 days, 9 hours, and 7 minutes.

In a moment you'll learn more about creating `timedelta` objects and about the operations you can do with them.

```python
from datetime import date
from datetime import datetime

d1 = date(2020, 11, 4)
d2 = date(2019, 11, 4)

print(d1 - d2)

dt1 = datetime(2020, 11, 4, 0, 0, 0)
dt2 = datetime(2019, 11, 4, 14, 53, 0)

print(dt1 - dt2)

```
-     
    

# Creating timedelta objects

You've already learned that a `timedelta` object can be returned as a result of subtracting two `date` or `datetime` objects.

Of course, you can also create an object yourself. For this purpose, let's get acquainted with the arguments accepted by the class constructor, which are: `days`, `seconds`, `microseconds`, `milliseconds`, `minutes`, `hours`, and `weeks`. Each of them is optional and defaults to 0.

The arguments should be integers or floating point numbers, and can be either positive or negative. Let's look at a simple example in the editor.

Result:

`16 days, 3:00:00`

**output**

The result of 16 days is obtained by converting the `weeks` argument to days (2 weeks = 14 days) and adding the `days` argument (2 days). This is normal behavior, because the `timedelta` object only stores days, seconds, and microseconds internally. Similarly, the `hour` argument is converted to minutes. Take a look at the example below:

`from datetime import timedelta`

`delta = timedelta(weeks=2, days=2, hours=3)`

`print("Days:", delta.days)`

`print("Seconds:", delta.seconds)`

`print("Microseconds:", delta.microseconds)`

Result:

`Days: 16 Seconds: 10800 Microseconds: 0`

**output**

The result of 10800 is obtained by converting 3 hours into seconds. In this way the `timedelta` object stores the arguments passed during its creation. Weeks are converted to days, hours and minutes to seconds, and milliseconds to microseconds.
```python
from datetime import timedelta

delta = timedelta(weeks=2, days=2, hours=3)
print(delta)

```
# Creating timedelta objects: continued

You already know how the `timedelta` object stores the passed arguments internally. It's time to see how it can be used in practice.

Let's look at some operations supported by the `datetime` module classes. Run the code we've provided in the editor.

Result:

`16 days, 2:00:00 32 days, 4:00:00 2019-11-05 2019-11-05 18:53:00`

**output**

The `timedelta` object can be multiplied by an integer. In our example, we multiply the object representing 16 days and 2 hours by 2. As a result, we receive a `timedelta` object representing 32 days and 4 hours.

Note that both days and hours have been multiplied by 2. Another interesting operation using the `timedelta` object is adding. In the example, we've added the `timedelta` object to the _date_ and `datetime` objects.

As a result of these operations, we receive _date_ and `datetime` objects increased by days and hours stored in the `timedelta` object.

The presented multiplication operation allows you to quickly increase the value of the `timedelta` object, while multiplication can also help you get a date from the future.

Of course, the `timedelta`, `date`, and `datetime` classes support many more operations. We encourage you to familiarize yourself with them in the documentation.

```python
from datetime import timedelta
from datetime import date
from datetime import datetime

delta = timedelta(weeks=2, days=2, hours=2)
print(delta)

delta2 = delta * 2
print(delta2)

d = date(2019, 10, 4) + delta2
print(d)

dt = datetime(2019, 10, 4, 14, 53) + delta2
print(dt)

```
##   
Estimated time

15-45 min

## Level of difficulty

Easy

## Objectives

-   improving the student's skills in date and time formatting;
-   improving the student's skills in using the `strftime` method.

## Scenario

During this course, you learned about the `strftime` method, which requires knowledge of directives to create a format. It's time to put the known directives into practice.

By the way, you'll have the opportunity to practice working with documentation, because you'll have to find directives that you don't yet know.

**Here's your task:**

Write a program that creates a `datetime` object for November 4, 2020 , 14:53:00. The object created should call the `strftime` method with the appropriate format to display the following result:

`2020/11/04 14:53:00 20/November/04 14:53:00 PM Wed, 2020 Nov 04 Wednesday, 2020 November 04 Weekday: 3 Day of the year: 309 Week number of the year: 44`

**expected output**

**Note:** Each result line should be created by calling the _strftime_ method with at least one directive in the format argument.
# Key takeaways

1. To create a `date` object, you must pass the year, month, and day arguments as follows:

`from datetime import date`

`my_date = date(2020, 9, 29)`

`print("Year:", my_date.year) # Year: 2020`

`print("Month:", my_date.month) # Month: 9`

`print("Day:", my_date.day) # Day: 29`

The `date` object has three (read-only) attributes: year, month, and day.

  

2. The `today` method returns a date object representing the current local date:

`from datetime import date`

`print("Today:", date.today()) # Displays: Today: 2020-09-29`

  

3. In Unix, the timestamp expresses the number of seconds since January 1, 1970, 00:00:00 (UTC). This date is called the "Unix epoch", because it began the counting of time on Unix systems. The timestamp is actually the difference between a particular date (including time) and January 1, 1970, 00:00:00 (UTC), expressed in seconds. To create a date object from a timestamp, we must pass a Unix timestamp to the `fromtimestamp` method:

`from datetime import date`

`import time`

`timestamp = time.time()`

`d = date.fromtimestamp(timestamp)`

Note: The `time` function returns the number of seconds from January 1, 1970 to the current moment in the form of a float number.

  

4. The constructor of the `time` class accepts six arguments (_hour_, _minute_, _second_, _microsecond_, _tzinfo_, and _fold_). Each of these arguments is optional.

`from datetime import time`

`t = time(13, 22, 20)`

`print("Hour:", t.hour) # Hour: 13`

`print("Minute:", t.minute) # Minute: 22`

`print("Second:", t.second) # Second: 20`

  

5. The `time` module contains the `sleep` function, which suspends program execution for a given number of seconds, e.g.:

`import time`

`time.sleep(10)`

`print("Hello world!") # This text will be displayed after 10 seconds.`

  

6. In the `datetime` module, date and time can be represented either as separate objects, or as one object. The class that combines date and time is called _datetime_. All arguments passed to the constructor go to read-only class attributes. They are _year_, _month_, _day_, _hour_, _minute_, _second_, _microsecond_, _tzinfo_, and _fold_:

`from datetime import datetime`

`dt = datetime(2020, 9, 29, 13, 51)`

`print("Datetime:", dt) # Displays: Datetime: 2020-09-29 13:51:00`

  

7. The `strftime` method takes only one argument in the form of a string specifying a format that can consist of directives. A directive is a string consisting of the character `%` (percent) and a lowercase or uppercase letter. Below are some useful directives:

-   `%Y` – returns the year with the century as a decimal number;
-   `%m` – returns the month as a zero-padded decimal number;
-   `%d` – returns the day as a zero-padded decimal number;
-   `%H` – returns the hour as a zero-padded decimal number;
-   `%M` – returns the minute as a zero-padded decimal number;
-   `%S` – returns the second as a zero-padded decimal number.

Example:

`from datetime import date`

`d = date(2020, 9, 29)`

`print(d.strftime('%Y/%m/%d')) # Displays: 2020/09/29`

  

8. It's possible to perform calculations on `date` and `datetime` objects, e.g.:

`from datetime import date`

`d1 = date(2020, 11, 4)`

`d2 = date(2019, 11, 4)`

`d = d1 - d2`

`print(d) # Displays: 366 days, 0:00:00.`

`print(d * 2) # Displays: 732 days, 0:00:00.`

The result of the subtraction is returned as a `timedelta` object that expresses the difference in days between the two dates in the example above.

Note that the difference in hours, minutes, and seconds is also displayed. The `timedelta` object can be used for further calculations (e.g. you can multiply it by 2).

  
  

  

**Exercise 1**

What is the output of the following snippet?

`from datetime import time t = time(14, 39) print(t.strftime("%H:%M:%S"))`

Check

`14:53:00`

  
  

**Exercise 2**

What is the output of the following snippet?

`from datetime import datetime dt1 = datetime(2020, 9, 29, 14, 41, 0) dt2 = datetime(2020, 9, 28, 14, 41, 0) print(dt1 - dt2)`

Check

`1 day, 0:00:00`

# Introduction to the calendar module

In addition to the `datetime` and `time` modules, the Python standard library provides a module called `calendar` which, as the name suggests, offers **calendar-related functions**.

One of them is of course displaying the calendar. It's important that the days of the week are displayed from Monday to Sunday, and each day of the week has its representation in the form of an integer:
![[Pasted image 20221224135614.png]]
The table above shows the representation of the days of the week in the `calendar` module. The first day of the week (Monday) is represented by the value _0_ and the _calendar.MONDAY_ constant, while the last day of the week (Sunday) is represented by the value _6_ and the _calendar.SUNDAY_ constant.

![[Pasted image 20221224135638.png]]
For months, integer values are indexed from 1, i.e., January is represented by 1, and December by 12. Unfortunately, there aren't constants that express the months.

The above information will be useful to you when working with the `calendar` module in this part of the course, but first let's start with some simple calendar examples.
# Your first calendar

You will start your adventure with the `calendar` module with a simple function called `calendar`, which allows you to **display the calendar for the whole year**. Let's look at how to use it to display the calendar for 2020. Run the code in the editor and see what happens.

The result displayed is similar to the result of the _cal_ command available in Unix. If you want to change the default calendar formatting, you can use the following parameters:

-   `w` – date column width (default 2)
-   `l` – number of lines per week (default 1)
-   `c` – number of spaces between month columns (default 6)
-   `m` – number of columns (default 3)

The calendar function requires you to specify the year, while the other parameters responsible for formatting are optional. We encourage you to try these parameters yourself.

A good alternative to the above function is the function called _prcal_, which also takes the same parameters as the `calendar` function, but doesn't require the use of the `print` function to display the calendar. Its use looks like this:

`import calendar`

`calendar.prcal(2020)`

`   `

```python
import calendar
print(calendar.calendar(2020))

```

# Calendar for a specific month

The `calendar` module has a function called `month`, which allows you to display a calendar for a specific month. Its use is really simple, you just need to specify the year and month - check out the code in the editor.

The example displays the calendar for November 2020. As in the `calendar` function, you can change the default formatting using the following parameters:

-   `w` – date column width (default 2)
-   `l` – number of lines per week (default 1)

**Note:** You can also use the `prmonth` function, which has the same parameters as the `month` function, but doesn't require you to use the `print` function to display the calendar.

```python
import calendar
print(calendar.month(2020, 11))

```
# The setfirstweekday() function

As you already know, by default in the `calendar` module, the first day of the week is Monday. However, you can change this behavior using a function called `setfirstweekday`.

Do you remember the table showing the days of the week and their representation in the form of integer values? It's time to use it, because the `setfirstweekday` method requires a parameter expressing the day of the week in the form of an integer value. Take a look at the example in the editor.

The example uses the `calendar.SUNDAY` constant, which contains a value of _6_. Of course, you could pass this value directly to the `setfirstweekday` function, but the version with a constant is more elegant.

As a result, we get a calendar showing the month of December 2020, in which the first day of all the weeks is Sunday.
```python
import calendar

calendar.setfirstweekday(calendar.SUNDAY)
calendar.prmonth(2020, 12)

```
# The weekday() function

Another useful function provided by the `calendar` module is the function called `weekday`, which returns the day of the week as an integer value for the given year, month, and day. Let's see it in practice.

Run the code in the editor to check the day of the week that falls on December 24, 2020.

Result:

`3`

**output**

The `weekday` function returns 3, which means that December 24, 2020 is a Thursday.
```python
import calendar
print(calendar.weekday(2020, 12, 24))

```
# The weekheader() function

You've probably noticed that the calendar contains weekly headers in a shortened form. If needed, you can get short weekday names using the `weekheader` method.

The `weekheader` method requires you to specify the width in characters for one day of the week. If the width you provide is greater than 3, you'll still get the abbreviated weekday names consisting of three characters.

So let's look at how to get a smaller header. Run the code in the editor.

Result:

`Mo Tu We Th Fr Sa Su`

**output**

**Note:** If you change the first day of the week, e.g., using the `setfirstweekday` function, it'll affect the result of the `weekheader` function.
```python
import calendar
print(calendar.weekheader(2))

```
# How do we check if a year is a leap year?

The `calendar` module provides two useful functions to check whether years are leap years.
![[Pasted image 20221224135943.png]]
  
The first one, called `isleap`, returns _True_ if the passed year is leap, or _False_ otherwise. The second one, called `leapdays`, returns the number of leap years in the given range of years.

Run the code in the editor.

Result:

`True 3`

**output**

In the example, we obtain the result 3, because in the period from 2010 to 2020 there are only three leap years (note: 2021 is not included). They are the years 2012, 2016, and 2020.

```python
import calendar

print(calendar.isleap(2020))
print(calendar.leapdays(2010, 2021))  # Up to but not including 2021.

```
# Classes for creating calendars

The presented functions aren't everything the `calendar` module offers. In addition to them, we can use the following classes:

-   `calendar.Calendar` – provides methods to prepare calendar data for formatting;
-   `calendar.TextCalendar` – is used to create regular text calendars;
-   `calendar.HTMLCalendar` – is used to create HTML calendars;
-   `calendar.LocalTextCalendar` – is a subclass of the `calendar.TextCalendar` class. The constructor of this class takes the _locale_ parameter, which is used to return the appropriate months and weekday names.
-   `calendar.LocalHTMLCalendar` – is a subclass of the `calendar.HTMLCalendar` class. The constructor of this class takes the locale parameter, which is used to return the appropriate months and weekday names.

During this course, you've already had the opportunity to create text calendars when discussing the functions of the `calendar` module.

Time to try something new. Let's take a closer look at the methods of the `calendar` class.

![[Pasted image 20221224140004.png]]
# Creating a Calendar object

The `Calendar` class constructor takes one optional parameter named `firstweekday`, by default equal to 0 (Monday).

The `firstweekday` parameter must be an integer between 0-6. For this purpose, we can use the already-known constants - look at the code in the editor.

The program will output the following result:

`6 0 1 2 3 4 5`

**output**

The code example uses the `Calendar` class method named `iterweekdays`, which returns an iterator for week day numbers.

The first value returned is always equal to the value of the `firstweekday` property. Because in our example the first value returned is 6, it means that the week starts on a Sunday.
```python
import calendar  

c = calendar.Calendar(calendar.SUNDAY)

for weekday in c.iterweekdays():
    print(weekday, end=" ")

```
# The itermonthdates() method

The `Calendar` class has several methods that return an iterator. One of them is the `itermonthdates` method, which requires specifying the year and month.

As a result, all days in the specified month and year are returned, as well as all days before the beginning of the month or the end of the month that are necessary to get a complete week.

Each day is represented by a `datetime.date` object. Take a look at the example in the editor.

The code displays all days in November 2019. Because the first day of November 2019 was a Friday, the following days are also returned to get the complete week: 10/28/2019 (Monday) 10/29/2019 (Tuesday) 10/30/2019 (Wednesday) 10/31/2019 (Thursday).

The last day of November 2019 was a Saturday, so in order to keep the complete week, one more day is returned 12/01/2019 (Friday).

```python
import calendar  

c = calendar.Calendar()

for date in c.itermonthdates(2019, 11):
    print(date, end=" ")

```
# Other methods that return iterators

Another useful method in the `Calendar` class is the method called `itermonthdates`, which takes year and month as parameters, and then returns the iterator to the days of the week represented by numbers.

Take a look at the example in the editor.

You’ll have certainly noticed the large number of 0s returned as a result of the example code. These are days outside the specified month range that are added to keep the complete week.

The first four zeros represent 10/28/2019 (Monday) 10/29/2019 (Tuesday) 10/30/2019 (Wednesday) 10/31/2019 (Thursday). The remaining numbers are days in the month, except the last value of 0, which replaces the date 12/01/2019 (Sunday).

There are four other similar methods in the `Calendar` class that differ in data returned:

-   `itermonthdates2` – returns days in the form of tuples consisting of a day of the month number and a week day number;
-   `itermonthdates3` – returns days in the form of tuples consisting of a year, a month, and a day of the month numbers. This method has been available since version 3.7;
-   `itermonthdates4` – returns days in the form of tuples consisting of a year, a month, a day of the month, and a day of the week numbers. This method has been available since Python version 3.7.

For testing purposes, use the example above and see how the return values of the described methods look in practice.

```python
import calendar  

c = calendar.Calendar()

for iter in c.itermonthdays(2019, 11):
    print(iter, end=" ")

```
# The monthdays2calendar() method

The `Calendar` class has several other useful methods that you can learn more about in the documentation ([https://docs.python.org/3/library/calendar.html](https://docs.python.org/3/library/calendar.html)).

One of them is the `monthdays2calendar` method, which takes the year and month, and then returns a list of weeks in a specific month. Each week is a tuple consisting of day numbers and weekday numbers. Look at the code in the editor.

Note that the days numbers outside the month are represented by 0, while the weekday numbers are a number from 0-6, where 0 is Monday and 6 is Sunday.

In a moment, this method may be useful for you to complete a laboratory task. Are you ready?

```python
import calendar  

c = calendar.Calendar()

for data in c.monthdays2calendar(2020, 12):
    print(data)

```
##   
Estimated time

30-60 minutes

## Level of difficulty

Easy

## Objectives

-   Improving the student's skills in using the _Calendar_ class.

## Scenario

During this course, we looked at the `Calendar` class a bit. Your task is to extend its functionality with a new method called `count_weekday_in_year`, which takes a year and a weekday as parameters, and then returns the number of occurrences of a specific weekday in the year.

Use the following tips:

-   Create a class called `MyCalendar` that extends the `Calendar` class;
-   create the `count_weekday_in_year` method with the year and weekday parameters. The weekday parameter should be a value between 0-6, where 0 is Monday and 6 is Sunday. The method should return the number of days as an integer;
-   in your implementation, use the `monthdays2calendar` method of the `Calendar` class.

The following are the expected results:

**Sample arguments**

`year=2019, weekday=0`

**Expected output**

`52`

  

**Sample arguments**

`year=2000, weekday=6`

**Expected output**

`53`

# Key takeaways

1. In the `calendar` module, the days of the week are displayed from Monday to Sunday. Each day of the week has its representation in the form of an integer, where the first day of the week (Monday) is represented by the value 0, while the last day of the week (Sunday) is represented by the value 6.

  

2. To display a calendar for any year, call the `calendar` function with the year passed as its argument, e.g.:

`import calendar`

`print(calendar.calendar(2020))`

Note: A good alternative to the above function is the function called `prcal`, which also takes the same parameters as the `calendar` function, but doesn't require the use of the `print` function to display the calendar.

  

3. To display a calendar for any month of the year, call the `month` function, passing year and month to it. For example:

`import calendar`

`print(calendar.month(2020, 9))`

Note: You can also use the `prmonth` function, which has the same parameters as the `month` function, but doesn't require the use of the `print` function to display the calendar.

  

4. The `setfirstweekday` function allows you to change the first day of the week. It takes a value from 0 to 6, where 0 is Sunday and 6 is Saturday.

  

5. The result of the `weekday` function is a day of the week as an integer value for a given year, month, and day:

`import calendar`

`print(calendar.weekday(2020, 9, 29)) # This displays 1, which means Tuesday.`

  

6. The `weekheader` function returns the weekday names in a shortened form. The `weekheader` method requires you to specify the width in characters for one day of the week. If the width you provide is greater than 3, you'll still get the abbreviated weekday names consisting of only three characters. For example:

`import calendar`

`print(calendar.weekheader(2)) # This display: Mo Tu We Th Fr Sa Su`

  

7. A very useful function available in the `calendar` module is the function called `isleap`, which, as the name suggests, allows you to check whether the year is a leap year or not:

`import calendar`

`print(calendar.isleap(2020)) # This displays: True`

  

8. You can create a `calendar` object yourself using the `Calendar` class, which, when creating its object, allows you to change the first day of the week with the optional `firstweekday` parameter, e.g.:

`import calendar`

`c = calendar.Calendar(2)`

`for weekday in c.iterweekdays():`

`print(weekday, end=" ")`

`# Result: 2 3 4 5 6 0 1`

The `iterweekdays` returns an iterator for weekday numbers. The first value returned is always equal to the value of the `firstweekday` property.

  
  

  

**Exercise 1**

What is the output of the following snippet?

`import calendar print(calendar.weekheader(1))`

Check

`M T W T F S S`

  
  

**Exercise 2**

What is the output of the following snippet?

`import calendar c = calendar.Calendar() for weekday in c.iterweekdays(): print(weekday, end=" ")`

Check

`0 1 2 3 4 5 6`

