---
part: "4.5"
topic: functions
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #functions  #introduction
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# Passing data from one function to another

When a program contains multiple functions, the question arises: 

How do you pass data from one function to another?

The following example asks the user for some integer values. The program then prints out these values and performs an "analysis" on them. The program is divided into three separate functions:

```python
def input_from_user(how_many: int):
    print(f"Please type in {how_many} numbers:")
    numbers = []

    for i in range(how_many):
        number = int(input(f"Number {i+1}: "))
        numbers.append(number)

    return numbers

def print_result(numbers: list):
    print("The numbers are: ")
    for number in numbers:
        print(number)

def analyze(numbers: list):
    mean = sum(numbers) / len(numbers)
    return f"There are altogether {len(numbers)} numbers, the mean is {mean}, the smallest is {min(numbers)} and the greatest is {max(numbers)}"

# the "main function" using these functions
inputs = input_from_user(5)
print_result(inputs)
analysis_result = analyze(inputs)
print(analysis_result)
```

- The main function "Saves" all data processed by the program. All that is needed is the input from the user in the variable ___inputs___
- (__If the input is needed in a function, it is passed as an argument.__)
- This happens with the functions ___print\_result___ and ___analyze___. 
- (__If the function produces data that is needed elsewhere in the program, the function returns it with the ___return___ __command.__)
- and it is stored in a variable in the main function. This happens with the functions ___input\_from\_user___ and ___analyze___.

## Why is global variables bad?

It is a bad idea to use a global variable
If _functions_ are able to change a __global variable__, unexpected things may start happening in the program, especially when the number of functions glow large.

Mutable global state is evil for many reasons ([Link](https://softwareengineering.stackexchange.com/questions/148108/why-is-global-state-so-evil)):

- **Bugs from mutable global state** - a lot of tricky bugs are caused by mutability. Bugs that can be caused by mutation from anywhere in the program are even tricker, as it's often hard to track down the exact cause
- **Poor testability** - if you have mutable global state, you will need to configure it for any tests that you write. This makes testing harder (and people being people are therefore less likely to do it!). e.g. in the case of application-wide database credentials, what if one test needs to access a specific test database different from everything else?
- **Inflexibility** - what if one part of the code requires one value in the global state, but another part requires another value (e.g. a temporary value during a transaction)? You suddenly have a nasty bit of refactoring on your hands
- **Function impurity** - "pure" functions (i.e. ones where the result depends only on the input parameters and have no side effects) are much easier to reason about and compose to build larger programs. Functions that read or manipulate mutable global state are inherently impure.
- **Code comprehension** - code behaviour that depends on a lot of mutable global variables is much trickier to understand - you need to understand the range of possible interactions with the global variable before you can reason about the behaviour of the code. In some situations, this problem can become intractable.
- **Concurrency issues** - mutable global state typically requires some form of locking when used in a concurrent situation. This is very hard to get right (is a cause of bugs) and adds considerably more complexity to your code (hard/expensive to maintain).
- **Performance** - multiple threads continually bashing on the same global state causes cache contention and will slow down your system overall.

Alternatives to mutable global state:

- **Function parameters** - often overlooked, but parameterising your functions better is often the best way to avoid global state. It forces you to solve the important conceptual question: what information does this function require to do its job? Sometimes it makes sense to have a data structure called "Context" that can be passed down a chain of functions that wraps up all relevant information.
- **Dependency injection** - same as for function parameters, just done a bit earlier (at object construction rather than function invocation). Be careful if your dependencies are mutable objects though, this can quickly cause the same problems as mutable global state.....
- **Immutable global state** is mostly harmless - it is effectively a constant. But make sure that it really is a constant, and that you aren't going to be tempted to turn it into mutable global state at a later point!
- **Immutable singletons** - pretty much the same as immutable global state, except that you can defer instantiation until they are needed. Useful for e.g. large fixed data structures that need expensive one-off pre-calculation. Mutable singletons are of course equivalent to mutable global state and are therefore evil :-)
- **Dynamic binding** - only available in some langauges like Common Lisp/Clojure, but this effectively lets you bind a value within a controlled scope (typically on a thread-local basis) which does not affect other threads. To some extent this is a "safe" way of getting the same effect as a global variable, since you know that only the current thread of execution will be affected. This is particularly useful in the case where you have multiple threads each handling independent transactions, for example.

> Passing data into and out of functions is best handled by arguments and return values.

You could also separate the implicit main function in the example above into its own function. 
Then the variable ___inputs___ would no longer be a global variable, but instead a local variable within the ___main___ function:

```python
def main():
	inputs = input_from_user(5)
	print_result(inputs)
	analysis_result = analyze(inputs)

	print(analysis_result)

main()
```