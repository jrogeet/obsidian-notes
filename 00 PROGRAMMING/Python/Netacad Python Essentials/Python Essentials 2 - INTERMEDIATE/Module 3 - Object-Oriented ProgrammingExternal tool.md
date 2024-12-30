
# Python Essentials 2:  
Module 3

**Object-Oriented Programming**

In this module, you will learn about:

-   Basic concepts of object-oriented programming (OOP)
-   The differences between the procedural and object approaches (motivations and profits)
-   Classes, objects, properties, and methods;
-   Designing reusable classes and creating objects;
-   Inheritance and polymorphism;
-   Exceptions as objects.
![[Pasted image 20221224111919.png]]
# The basic concepts of the object-oriented approach

Let's take a step outside of computer programming and computers in general, and discuss object programming issues.

Nearly all of the programs and techniques you have used till now fall under the procedural style of programming. Admittedly, you have made use of some built-in objects, but when referring to them, we just mentioned the absolute minimum.

The procedural style of programming was the dominant approach to software development for decades of IT, and it is still in use today. Moreover, it isn't going to disappear in the future, as it works very well for specific types of projects (generally, not very complex ones and not large ones, but there are lots of exceptions to that rule).

The object approach is quite young (much younger than the procedural approach) and is particularly useful when applied to big and complex projects carried out by large teams consisting of many developers.

This kind of understanding of a project's structure makes many important tasks easier, e.g., dividing the project into small, independent parts, and independent development of different project elements.

**Python is a universal tool for both object and procedural programming**. It may be successfully utilized in both spheres.

  

  

Furthermore, you can create lots of useful applications, even if you know nothing about classes and objects, but you have to keep in mind that some of the problems (e.g., graphical user interface handling) may require a strict object approach.

Fortunately, object programming is relatively simple.

![[Pasted image 20221224111932.png]]
# Procedural vs. the object-oriented approach

In the **procedural approach**, it's possible to distinguish two different and completely separate worlds: **the world of data, and the world of code**. The world of data is populated with variables of different kinds, while the world of code is inhabited by code grouped into modules and functions.

Functions are able to use data, but not vice versa. Furthermore, functions are able to abuse data, i.e., to use the value in an unauthorized manner (e.g., when the sine function gets a bank account balance as a parameter).

We said in the past that data cannot use functions. But is this entirely true? Are there some special kinds of data that can use functions?

Yes, there are - the ones named methods. These are functions which are invoked from within the data, not beside them. If you can see this distinction, you've taken the first step into object programming.

The **object approach** suggests a completely different way of thinking. The data and the code are enclosed together in the same world, divided into classes.

Every **class is like a recipe which can be used when you want to create a useful object** (this is where the name of the approach comes from). You may produce as many objects as you need to solve your problem.

Every object has a set of traits (they are called properties or attributes - we'll use both words synonymously) and is able to perform a set of activities (which are called methods).

The recipes may be modified if they are inadequate for specific purposes and, in effect, new classes may be created. These new classes inherit properties and methods from the originals, and usually add some new ones, creating new, more specific tools.

  

  

**Objects are incarnations** of ideas expressed in classes, like a cheesecake on your plate is an incarnation of the idea expressed in a recipe printed in an old cookbook.

The objects interact with each other, exchanging data or activating their methods. A properly constructed class (and thus, its objects) are able to protect the sensible data and hide it from unauthorized modifications.

There is no clear border between data and code: they live as one in objects.

All these concepts are not as abstract as you may at first suspect. On the contrary, they all are taken from real-life experiences, and therefore are extremely useful in computer programming: they don't create artificial life - **they reflect real facts, relationships, and circumstances**.

![[Pasted image 20221224111946.png]]
# Class hierarchies

The word _class_ has many meanings, but not all of them are compatible with the ideas we want to discuss here. The _class_ that we are concerned with is like a _category_, as a result of precisely defined similarities.

We'll try to point out a few classes which are good examples of this concept.
![[Pasted image 20221224111958.png]]
Let's look for a moment at vehicles. All existing vehicles (and those that don't exist yet) are **related by a single, important feature**: the ability to move. You may argue that a dog moves, too; is a dog a vehicle? No, it isn't. We have to improve the definition, i.e., enrich it with other criteria, distinguishing vehicles from other beings, and creating a stronger connection. Let's take the following circumstances into consideration: vehicles are artificially created entities used for transportation, moved by forces of nature, and directed (driven) by humans.

Based on this definition, a dog is not a vehicle.

The _vehicles_ class is very broad. Too broad. We have to define some more **specialized classes**, then. The specialized classes are the **subclasses**. The _vehicles_ class will be a **superclass** for them all.

  

  

Note: **the hierarchy grows from top to bottom, like tree roots, not branches**. The most general, and the widest, class is always at the top (the superclass) while its descendants are located below (the subclasses).

By now, you can probably point out some potential subclasses for the _Vehicles_ superclass. There are many possible classifications. We've chosen subclasses based on the environment, and say that there are (at least) four subclasses:

-   land vehicles;
-   water vehicles;
-   air vehicles;
-   space vehicles.

In this example, we'll discuss the first subclass only - land vehicles. If you wish, you can continue with the remaining classes.

Land vehicles may be further divided, depending on the method with which they impact the ground. So, we can enumerate:

-   wheeled vehicles;
-   tracked vehicles;
-   hovercrafts.

The hierarchy we've created is illustrated by the figure.

Note the direction of the arrows - they always point to the superclass. The top-level class is an exception - it doesn't have its own superclass.

# Class hierarchies: continued

Another example is the hierarchy of the taxonomic kingdom of animals.

We can say that all _animals_ (our top-level class) can be divided into five subclasses:

-   mammals;
-   reptiles;
-   birds;
-   fish;
-   amphibians.

We'll take the first one for further analysis.

We have identified the following subclasses:

-   wild mammals;
-   domesticated mammals.
![[Pasted image 20221224112015.png]]
  
Try to extend the hierarchy any way you want, and find the right place for humans.
# What is an object?

A class (among other definitions) is a **set of objects**. An object is **a being belonging to a class**.

An object is **an incarnation of the requirements, traits, and qualities assigned to a specific class**. This may sound simple, but note the following important circumstances. Classes form a hierarchy.

This may mean that an object belonging to a specific class belongs to all the superclasses at the same time. It may also mean that any object belonging to a superclass may not belong to any of its subclasses.

For example: any personal car is an object belonging to the _wheeled vehicles_ class. It also means that the same car belongs to all superclasses of its home class; therefore, it is a member of the _vehicles_ class, too.

Your dog (or your cat) is an object included in the _domesticated mammals_ class, which explicitly means that it is included in the _animals_ class as well.

Each **subclass is more specialized** (or more specific) than its superclass. Conversely, each **superclass is more general** (more abstract) than any of its subclasses.

Note that we've presumed that a class may only have one superclass - this is not always true, but we'll discuss this issue more a bit later.

  
  

## Inheritance

Let's define one of the fundamental concepts of object programming, named **inheritance**. Any object bound to a specific level of a class hierarchy **inherits all the traits (as well as the requirements and qualities) defined inside any of the superclasses**.

The object's home class may define new traits (as well as requirements and qualities) which will be inherited by any of its subclasses.

![[Pasted image 20221224112032.png]]
You shouldn't have any problems matching this rule to specific examples, whether it applies to animals, or to vehicles.
# What does an object have?

The object programming convention assumes that **every existing object may be equipped with three groups of attributes**:

-   an object has a **name** that uniquely identifies it within its home namespace (although there may be some anonymous objects, too)
-   an object has a **set of individual properties** which make it original, unique, or outstanding (although it's possible that some objects may have no properties at all)
-   an object has a **set of abilities to perform specific activities**, able to change the object itself, or some of the other objects.

There is a hint (although this doesn't always work) which can help you identify any of the three spheres above. Whenever you describe an object and you use:

-   a noun – you probably define the object's name;
-   an adjective – you probably define the object's property;
-   a verb – you probably define the object's activity.

Two sample phrases should serve as a good example:

-   A pink Cadillac went quickly.  
      
    Object name = Cadillac  
    Home class = Wheeled vehicles  
    Property = Color (pink)  
    Activity = Go (quickly)

  
  

  

-   Rudolph is a large cat who sleeps all day.  
      
    Object name = Rudolph  
    Home class = Cat  
    Property = Size (large)  
    Activity = Sleep (all day)

![[Pasted image 20221224112053.png]]
# Your first class

Object programming is **the art of defining and expanding classes**. A class is a model of a very specific part of reality, reflecting properties and activities found in the real world.

The classes defined at the beginning are too general and imprecise to cover the largest possible number of real cases.

There's no obstacle to defining new, more precise subclasses. They'll inherit everything from their superclass, so the work that went into its creation isn't wasted.

The new class may add new properties and new activities, and therefore may be more useful in specific applications. Obviously, it may be used as a superclass for any number of newly created subclasses.

The process doesn't need to have an end. You can create as many classes as you need.

The class you define has nothing to do with the object: **the existence of a class does not mean that any of the compatible objects will automatically be created**. The class itself isn't able to create an object - you have to create it yourself, and Python allows you to do this.

It's time to define the simplest class and to create an object. Take a look at the example below:

`   class TheSimplestClass:  pass       `  

We've defined a class there. The class is rather poor: it has neither properties nor activities. It's **empty**, actually, but that doesn't matter for now. The simpler the class, the better for our purposes.

**The definition begins with the keyword `class`**. The keyword is followed by an **identifier which will name the class** (note: don't confuse it with the object's name - these are two different things).

Next, you add a **colon** (`:`), as classes, like functions, form their own nested block. The content inside the block define all the class's properties and activities.

The `pass` keyword fills the class with nothing. It doesn't contain any methods or properties.

  
  

## Your first object

The newly defined class becomes a tool that is able to create new objects. The tool has to be used explicitly, on demand.

Imagine that you want to create one (exactly one) object of the `TheSimplestClass` class.

To do this, you need to assign a variable to store the newly created object of that class, and create an object at the same time.

You do it in the following way:

`   my_first_object = TheSimplestClass()       `  

Note:

-   the class name tries to pretend that it's a function - can you see this? We'll discuss it soon;
-   the newly created object is equipped with everything the class brings; as this class is completely empty, the object is empty, too.

The act of creating an object of the selected class is also called an **instantiation** (as the object becomes an **instance of the class**).

Let's leave classes alone for a short moment, as we're now going to tell you a few words about _stacks_. We know the concept of classes and objects may not be fully clear yet. Don't worry, we'll explain everything very soon.

# Key takeaways

  

1. A **class** is an idea (more or less abstract) which can be used to create a number of incarnations – such an incarnation is called an **object**.

  

2. When a class is derived from another class, their relation is named **inheritance**. The class which derives from the other class is named a **subclass**. The second side of this relation is named **superclass**. A way to present such a relation is an **inheritance diagram**, where:

-   superclasses are always presented **above** their subclasses;
-   relations between classes are shown as arrows directed **from the subclass toward its superclass**.

  

3. Objects are equipped with:

-   a **name** which identifies them and allows us to distinguish between them;
-   a set of **properties** (the set can be empty)
-   a set of **methods** (can be empty, too)

  

4. To define a Python class, you need to use the `class` keyword. For example:

`   class This_Is_A_Class:  pass   `  

5. To create an object of the previously defined class, you need to use the class as if it were a function. For example:

`   this_is_an_object = This_Is_A_Class()   `  

  

**Exercise 1**

If we assume that pythons, vipers, and cobras are subclasses of the same superclass, how would you call it?

Check  

Snake, reptile, vertebrate, animal – all these answers are acceptable.

  

**Exercise 2**

Try to name a few python class subclasses.

Check  

Indian python, African rock python, ball python, Burmese python – the list is long.

  

**Exercise 3**

Can you name one of your classes just "class"?

Check  

No, you can't – `class` is a keyword!

# What is a stack?

**A stack is a structure developed to store data in a very specific way**. Imagine a stack of coins. You aren't able to put a coin anywhere else but on the top of the stack.

Similarly, you can't get a coin off the stack from any place other than the top of the stack. If you want to get the coin that lies on the bottom, you have to remove all the coins from the higher levels.

The alternative name for a stack (but only in IT terminology) is **LIFO**.

It's an abbreviation for a very clear description of the stack's behavior: **Last In - First Out**. The coin that came last onto the stack will leave first.

**A stack is an object** with two elementary operations, conventionally named **push** (when a new element is put on the top) and **pop** (when an existing element is taken away from the top).

Stacks are used very often in many classical algorithms, and it's hard to imagine the implementation of many widely used tools without the use of stacks.

![[Pasted image 20221224112128.png]]
Let's implement a stack in Python. This will be a very simple stack, and we'll show you how to do it in two independent approaches: procedural and objective.

Let's start with the first one.

# The stack - the procedural approach

First, you have to decide how to store the values which will arrive onto the stack. We suggest using the simplest of methods, and **employing a list** for this job. Let's assume that the size of the stack is not limited in any way. Let's also assume that the last element of the list stores the top element.

The stack itself is already created:

`   stack = []       `  

We're ready to **define a function that puts a value onto the stack**. Here are the presuppositions for it:

-   the name for the function is `push`;
-   the function gets one parameter (this is the value to be put onto the stack)
-   the function returns nothing;
-   the function appends the parameter's value to the end of the stack;

This is how we've done it - take a look:

`   def push(val):  stack.append(val)       `  

Now it's time for a **function to take a value off the stack**. This is how you can do it:

-   the name of the function is pop;
-   the function doesn't get any parameters;
-   the function returns the value taken from the stack
-   the function reads the value from the top of the stack and removes it.

The function is here:

`   def pop():  val = stack[-1]  del stack[-1]  return val       `  

Note: the function doesn't check if there is any element in the stack.

Let's assemble all the pieces together to set the stack in motion. The **complete program** pushes three numbers onto the stack, pulls them off, and prints their values on the screen. You can see it in the editor window.

The program outputs the following text to the screen:

`1 2 3`

**output**

Test it.

```python
stack = []


def push(val):
    stack.append(val)


def pop():
    val = stack[-1]
    del stack[-1]
    return val


push(3)
push(2)
push(1)

print(pop())
print(pop())
print(pop())
```
# The stack - the procedural approach vs. the object-oriented approach

The procedural stack is ready. Of course, there are some weaknesses, and the implementation could be improved in many ways (harnessing exceptions to work is a good idea), but in general the stack is fully implemented, and you can use it if you need to.

But the more often you use it, the more disadvantages you'll encounter. Here are some of them:

-   the essential variable (the stack list) is highly **vulnerable**; anyone can modify it in an uncontrollable way, destroying the stack, in effect; this doesn't mean that it's been done maliciously - on the contrary, it may happen as a result of carelessness, e.g., when somebody confuses variable names; imagine that you have accidentally written something like this:  
      
    `   stack[0] = 0       `  
    The functioning of the stack will be completely disorganized;
  
-   it may also happen that one day you need more than one stack; you'll have to create another list for the stack's storage, and probably other `push` and `pop` functions too;
  
-   it may also happen that you need not only `push` and `pop` functions, but also some other conveniences; you could certainly implement them, but try to imagine what would happen if you had dozens of separately implemented stacks.

  

  

The objective approach delivers solutions for each of the above problems. Let's name them first:

-   the ability to hide (protect) selected values against unauthorized access is called **encapsulation; the encapsulated values can be neither accessed nor modified if you want to use them exclusively**;
  
-   when you have a class implementing all the needed stack behaviors, you can produce as many stacks as you want; you needn't copy or replicate any part of the code;
  
-   the ability to enrich the stack with new functions comes from inheritance; you can create a new class (a subclass) which inherits all the existing traits from the superclass, and adds some new ones.
![[Pasted image 20221224112202.png]]
Let's now write a brand new stack implementation from scratch. This time, we'll use the objective approach, guiding you step by step into the world of object programming.
-     
    

# The stack - the object approach

Of course, the main idea remains the same. We'll use a list as the stack's storage. We only have to know how to put the list into the class.

Let's start from the absolute beginning - this is how the objective stack begins:

`   class Stack:       `  

Now, we expect two things from it:

-   we want the class to have **one property as the stack's storage** - we have to **"install" a list inside each object of the class** (note: each object has to have its own list - the list mustn't be shared among different stacks)
-   then, we want **the list to be hidden** from the class users' sight.

How is this done?

In contrast to other programming languages, Python has no means of allowing you to declare such a property just like that.

Instead, you need to add a specific statement or instruction. The properties have to be added to the class manually.

How do you guarantee that such an activity takes place every time the new stack is created?

There is a simple way to do it - you have to **equip the class with a specific function** - its specificity is dual:

-   it has to be named in a strict way;
-   it is invoked implicitly, when the new object is created.

Such a function is called a **constructor**, as its general purpose is to **construct a new object**. The constructor should know everything about the object's structure, and must perform all the needed initializations.

Let's add a very simple constructor to the new class. Take a look at the snippet:

`   class Stack:  def __init__(self):  print("Hi!")  stack_object = Stack()       `  

And now:

-   the constructor's name is always `__init__`;
-   it has to have **at least one parameter** (we'll discuss this later); the parameter is used to represent the newly created object - you can use the parameter to manipulate the object, and to enrich it with the needed properties; you'll make use of this soon;
-   note: the obligatory parameter is usually named `self` - it's only **a convention, but you should follow it** - it simplifies the process of reading and understanding your code.

The code is in the editor. Run it now.

Here is its output:

`Hi!`

**output**

Note - there is no trace of invoking the constructor inside the code. It has been invoked implicitly and automatically. Let's make use of that now.
```python
class Stack:  # Defining the Stack class.
    def __init__(self):  # Defining the constructor function.
        print("Hi!")


stack_object = Stack()  # Instantiating the object.

```
# The stack - the object approach: continued

Any change you make inside the constructor that modifies the state of the `self` parameter will be reflected in the newly created object.

This means you can add any property to the object and the property will remain there until the object finishes its life or the property is explicitly removed.

Now let's **add just one property to the new object** - a list for a stack. We'll name it `stack_list`.

Just like here:

`   class Stack:  def __init__(self):  self.stack_list = []  stack_object = Stack()  print(len(stack_object.stack_list))       `  

Note:

-   we've used the **dotted notation**, just like when invoking methods; this is the general convention for accessing an object's properties - you need to name the object, put a dot (`.`) after it, and specify the desired property's name; don't use parentheses! You don't want to invoke a method - you want to **access a property**;
-   if you set a property's value for the very first time (like in the constructor), you are creating it; from that moment on, the object has got the property and is ready to use its value;
-   we've done something more in the code - we've tried to access the `stack_list` property from outside the class immediately after the object has been created; we want to check the current length of the stack - have we succeeded?

Yes, we have - the code produces the following output:

`0`

**output**

This is not we want from the stack. We prefer `stack_list` to be **hidden from the outside world**. Is that possible?

Yes, and it's simple, but not very intuitive.

```python
class Stack:
    def __init__(self):
        self.stack_list = []


stack_object = Stack()
print(len(stack_object.stack_list))

```
# The stack - the object approach: continued

Take a look - we've added two underscores before the `stack_list` name - nothing more:

`class Stack: def __init__(self): self.__stack_list = [] stack_object = Stack() print(len(stack_object.__stack_list))`  

The change invalidates the program.

Why?

When any class component has a **name starting with two underscores (`__`), it becomes private** - this means that it can be accessed only from within the class.

You cannot see it from the outside world. This is how Python implements the **encapsulation** concept.

Run the program to test our assumptions - an AttributeError exception should be raised.
```python
class Stack:
    def __init__(self):
        self.__stack_list = []


stack_object = Stack()
print(len(stack_object.__stack_list))
```
# The object approach: a stack from scratch

Now it's time for the two functions (methods) implementing the _push_ and _pop_ operations. Python assumes that a function of this kind (a class activity) should be **immersed inside the class body** - just like a constructor.

We want to invoke these functions to `push` and `pop` values. This means that they should both be accessible to every class's user (in contrast to the previously constructed list, which is hidden from the ordinary class's users).

Such a component is called **public**, so you **can't begin its name with two (or more) underscores**. There is one more requirement - **the name must have no more than one trailing underscore**. As no trailing underscores at all fully meets the requirement, you can assume that the name is acceptable.

The functions themselves are simple. Take a look:

`   class Stack:  def __init__(self):  self.__stack_list = []  def push(self, val):  self.__stack_list.append(val)  def pop(self):  val = self.__stack_list[-1]  del self.__stack_list[-1]  return val  stack_object = Stack()  stack_object.push(3)  stack_object.push(2)  stack_object.push(1)  print(stack_object.pop())  print(stack_object.pop())  print(stack_object.pop())       `  

However, there's something really strange in the code. The functions look familiar, but they have more parameters than their procedural counterparts.

Here, both functions have a parameter named `self` at the first position of the parameters list.

Is it needed? Yes, it is.

All methods have to have this parameter. It plays the same role as the first constructor parameter.

**It allows the method to access entities (properties and activities/methods) carried out by the actual object**. You cannot omit it. Every time Python invokes a method, it implicitly sends the current object as the first argument.

This means that a **method is obligated to have at least one parameter, which is used by Python itself** - you don't have any influence on it.

If your method needs no parameters at all, this one must be specified anyway. If it's designed to process just one parameter, you have to specify two, and the first one's role is still the same.

There is one more thing that requires explanation - the way in which methods are invoked from within the `__stack_list` variable.

Fortunately, it's much simpler than it looks:

-   the first stage delivers the object as a whole → `self`;
-   next, you need to get to the `__stack_list` list → `self.__stack_list`;
-   with `__stack_list` ready to be used, you can perform the third and last step → `self.__stack_list.append(val)`.

The class declaration is complete, and all its components have been listed. The class is ready for use.

```python
class Stack:
    def __init__(self):
        self.__stack_list = []


    def push(self, val):
        self.__stack_list.append(val)


    def pop(self):
        val = self.__stack_list[-1]
        del self.__stack_list[-1]
        return val


stack_object = Stack()

stack_object.push(3)
stack_object.push(2)
stack_object.push(1)

print(stack_object.pop())
print(stack_object.pop())
print(stack_object.pop())
```
# The object approach: a stack from scratch

Having such a class opens up some new possibilities. For example, you can now have more than one stack behaving in the same way. Each stack will have its own copy of private data, but will utilize the same set of methods.

This is exactly what we want for this example.

Analyze the code:

`class Stack: def __init__(self): self.__stack_list = [] def push(self, val): self.__stack_list.append(val) def pop(self): val = self.__stack_list[-1] del self.__stack_list[-1] return val stack_object_1 = Stack() stack_object_2 = Stack() stack_object_1.push(3) stack_object_2.push(stack_object_1.pop()) print(stack_object_2.pop())`  

There are **two stacks created from the same base class**. They work **independently**. You can make more of them if you want to.

Run the code in the editor and see what happens. Carry out your own experiments.

```python
class Stack:
    def __init__(self):
        self.__stack_list = []

    def push(self, val):
        self.__stack_list.append(val)

    def pop(self):
        val = self.__stack_list[-1]
        del self.__stack_list[-1]
        return val


stack_object_1 = Stack()
stack_object_2 = Stack()

stack_object_1.push(3)
stack_object_2.push(stack_object_1.pop())

print(stack_object_2.pop())
```
# The object approach: a stack from scratch (continued)

Analyze the snippet below - we've created three objects of the class `Stack`. Next, we've juggled them up. Try to predict the value outputted to the screen.

`   class Stack:  def __init__(self):  self.__stack_list = []  def push(self, val):  self.__stack_list.append(val)  def pop(self):  val = self.__stack_list[-1]  del self.__stack_list[-1]  return val  little_stack = Stack()  another_stack = Stack()  funny_stack = Stack()  little_stack.push(1)  another_stack.push(little_stack.pop() + 1)  funny_stack.push(another_stack.pop() - 2)  print(funny_stack.pop())   `  

So, what's the result? Run the program and check if you were right.
```python
class Stack:
    def __init__(self):
        self.__stack_list = []

    def push(self, val):
        self.__stack_list.append(val)

    def pop(self):
        val = self.__stack_list[-1]
        del self.__stack_list[-1]
        return val


# Enter code here.
```
# The object approach: a stack from scratch (continued)

Now let's go a little further. Let's **add a new class for handling stacks**.

The new class should be able to **evaluate the sum of all the elements currently stored on the stack**.

We don't want to modify the previously defined stack. It's already good enough in its applications, and we don't want it changed in any way. We want a new stack with new capabilities. In other words, we want to construct a subclass of the already existing `Stack` class.

The first step is easy: just **define a new subclass pointing to the class which will be used as the superclass**.

This is what it looks like:

`   class AddingStack(Stack):  pass       `  

The class doesn't define any new component yet, but that doesn't mean that it's empty. **It gets all the components defined by its superclass** - the name of the superclass is written before the colon directly after the new class name.

This is what we want from the new stack:

-   we want the `push` method not only to push the value onto the stack but also to add the value to the `sum` variable;
-   we want the `pop` function not only to pop the value off the stack but also to subtract the value from the `sum` variable.

  

Firstly, let's add a new variable to the class. It'll be a **private variable**, like the stack list. We don't want anybody to manipulate the `sum` value.

As you already know, adding a new property to the class is done by the constructor. You already know how to do that, but there is something really intriguing inside the constructor. Take a look:

`   class AddingStack(Stack):  def __init__(self):  Stack.__init__(self)  self.__sum = 0       `  

The second line of the constructor's body creates a property named `__sum` - it will store the total of all the stack's values.

But the line before it looks different. What does it do? Is it really necessary? Yes, it is.

Contrary to many other languages, Python forces you to **explicitly invoke a superclass's constructor**. Omitting this point will have harmful effects - the object will be deprived of the `__stack_list` list. Such a stack will not function properly.

This is the only time you can invoke any of the available constructors explicitly - it can be done inside the subclass's constructor.

Note the syntax:

-   you specify the superclass's name (this is the class whose constructor you want to run)
-   you put a dot (`.`)after it;
-   you specify the name of the constructor;
-   you have to point to the object (the class's instance) which has to be initialized by the constructor - this is why you have to specify the argument and use the `self` variable here; note: **invoking any method (including constructors) from outside the class never requires you to put the `self` argument at the argument's list** - invoking a method from within the class demands explicit usage of the `self` argument, and it has to be put first on the list.

Note: it's generally a recommended practice to invoke the superclass's constructor before any other initializations you want to perform inside the subclass. This is the rule we have followed in the snippet.
```python
class Stack:
    def __init__(self):
        self.__stack_list = []

    def push(self, val):
        self.__stack_list.append(val)

    def pop(self):
        val = self.__stack_list[-1]
        del self.__stack_list[-1]
        return val


class AddingStack(Stack):
    def __init__(self):
        Stack.__init__(self)
        self.__sum = 0
```
# The object approach: a stack from scratch (continued)

Secondly, let's add two methods. But let us ask you: is it really adding? We have these methods in the superclass already. Can we do something like that?

Yes, we can. It means that we're going to **change the functionality of the methods, not their names**. We can say more precisely that the interface (the way in which the objects are handled) of the class remains the same when changing the implementation at the same time.

Let's start with the implementation of the `push` function. This is what we expect from it:

-   to add the value to the `__sum` variable;
-   to push the value onto the stack.

Note: the second activity has already been implemented inside the superclass - so we can use that. Furthermore, we have to use it, as there's no other way to access the `__stackList` variable.

This is how the `push` method looks in the subclass:

`   def push(self, val):  self.__sum += val  Stack.push(self, val)       `  

Note the way we've invoked the previous implementation of the `push` method (the one available in the superclass):

-   we have to specify the superclass's name; this is necessary in order to clearly indicate the class containing the method, to avoid confusing it with any other function of the same name;
-   we have to specify the target object and to pass it as the first argument (it's not implicitly added to the invocation in this context.)

We say that the `push` method has been overridden - the same name as in the superclass now represents a different functionality.
```python
class Stack:
    def __init__(self):
        self.__stackList = []

    def push(self, val):
        self.__stackList.append(val)

    def pop(self):
        val = self.__stackList[-1]
        del self.__stackList[-1]
        return val


class AddingStack(Stack):
    def __init__(self):
        Stack.__init__(self)
        self.__sum = 0


# Enter code here.
```
# The object approach: a stack from scratch (continued)

This is the new `pop` function:

`   def pop(self):  val = Stack.pop(self)  self.__sum -= val  return val       `  

So far, we've defined the `__sum` variable, but we haven't provided a method to get its value. It seems to be hidden. How can we reveal it and do it in a way that still protects it from modifications?

We have to define a new method. We'll name it `get_sum`. Its only task will be to **return the `__sum` value**.

Here it is:

`   def get_sum(self):  return self.__sum       `  

So, let's look at the program in the editor. The complete code of the class is there. We can check its functioning now, and we do it with the help of a very few additional lines of code.

As you can see, we add five subsequent values onto the stack, print their sum, and take them all off the stack.

Okay, this has been a very brief introduction to Python's object programming. Soon we're going to tell you about it all in more detail.

```python
class Stack:
    def __init__(self):
        self.__stack_list = []

    def push(self, val):
        self.__stack_list.append(val)

    def pop(self):
        val = self.__stack_list[-1]
        del self.__stack_list[-1]
        return val


class AddingStack(Stack):
    def __init__(self):
        Stack.__init__(self)
        self.__sum = 0

    def get_sum(self):
        return self.__sum

    def push(self, val):
        self.__sum += val
        Stack.push(self, val)

    def pop(self):
        val = Stack.pop(self)
        self.__sum -= val
        return val


stack_object = AddingStack()

for i in range(5):
    stack_object.push(i)
print(stack_object.get_sum())

for i in range(5):
    print(stack_object.pop())
```
# Key takeaways

  

1. A **stack** is an object designed to store data using the **LIFO** model. The stack usually accomplishes at least two operations, named **push()** and **pop()**.

  

2. Implementing the stack in a procedural model raises several problems which can be solved by the techniques offered by **OOP** (**O**bject **O**riented **P**rogramming):

  

3. A class **method** is actually a function declared inside the class and able to access all the class's components.

  

4. The part of the Python class responsible for creating new objects is called the **constructor**, and it's implemented as a method of the name `__init__`.

  

5. Each class method declaration must contain at least one parameter (always the first one) usually referred to as `self`, and is used by the objects to identify themselves.

  

6. If we want to hide any of a class's components from the outside world, we should start its name with `__`. Such components are called **private**.

  

  

**Exercise 1**

Assuming that there is a class named `Snakes`, write the very first line of the `Python` class declaration, expressing the fact that the new class is actually a subclass of Snake.

Check

`class Python(Snakes):`

  
  

**Exercise 2**

Something is missing from the following declaration – what?

`class Snakes def __init__(): self.sound = 'Sssssss'`  
Check

The `__init__()` constructor lacks the obligatory parameter (we should name it `self` to stay compliant with the standards).

  
  

**Exercise 3**

Modify the code to guarantee that the `venomous` property is private.

`class Snakes def __init__(self): self.venomous = True`  
Check

The code should look as follows:  
  
`class Snakes def __init__(self): self.__venomous = True`

## Estimated time

20-45 minutes

## Level of difficulty

Easy/Medium

## Objectives

-   improve the student's skills in defining classes;
-   using existing classes to create new classes equipped with new functionalities.

## Scenario

We've showed you recently how to extend _Stack_ possibilities by defining a new class (i.e., a subclass) which retains all inherited traits and adds some new ones.

Your task is to extend the `Stack` class behavior in such a way so that the class is able to count all the elements that are pushed and popped (we assume that counting pops is enough). Use the `Stack` class we've provided in the editor.

Follow the hints:

-   introduce a property designed to count pop operations and name it in a way which guarantees hiding it;
-   initialize it to zero inside the constructor;
-   provide a method which returns the value currently assigned to the counter (name it `get_counter()`).

Complete the code in the editor. Run it to check whether your code outputs 100

```python
class Stack:
    def __init__(self):
        self.__stk = []

    def push(self, val):
        self.__stk.append(val)

    def pop(self):
        val = self.__stk[-1]
        del self.__stk[-1]
        return val


class CountingStack(Stack):
    def __init__(self):
    #
    # Fill the constructor with appropriate actions.
    #

    def get_counter(self):
    #
    # Present the counter's current value to the world.
    #

    def pop(self):
    #
    # Do pop and update the counter.
    #
	

stk = CountingStack()
for i in range(100):
    stk.push(i)
    stk.pop()
print(stk.get_counter())
```
## Estimated time

20-45 minutes

## Level of difficulty

Easy/Medium

## Objectives

-   improving the student's skills in defining classes from scratch;
-   implementing standard data structures as classes.

## Scenario

As you already know, a _stack_ is a data structure realizing the so-called LIFO (Last In - First Out) model. It's easy and you've already grown perfectly accustomed to it.

Let's taste something new now. A _queue_ is a data model characterized by the term **FIFO: First In - Fist Out**. Note: a regular queue (line) you know from shops or post offices works exactly in the same way - a customer who came first is served first too.

Your task is to implement the `Queue` class with two basic operations:

-   `put(element)`, which puts an element at end of the queue;
-   `get()`, which takes an element from the front of the queue and returns it as the result (the queue cannot be empty to successfully perform it.)

Follow the hints:

-   use a list as your storage (just like we did in stack)
-   `put()` should append elements to the beginning of the list, while `get()` should remove the elements from the list's end;
-   define a new exception named `QueueError` (choose an exception to derive it from) and raise it when `get()` tries to operate on an empty list.

Complete the code we've provided in the editor. Run it to check whether its output is similar to ours.

## Expected output

`1 dog False Queue error`

```python
class QueueError(???):  # Choose base class for the new exception.
    #
    #  Write code here
    #


class Queue:
    def __init__(self):
        #
        # Write code here
        #

    def put(self, elem):
        #
        # Write code here
        #

    def get(self):
        #
        # Write code here
        #


que = Queue()
que.put(1)
que.put("dog")
que.put(False)
try:
    for i in range(4):
        print(que.get())
except:
    print("Queue error")
```
## Estimated time

15-30 minutes

## Level of difficulty

Easy/Medium

## Objectives

-   improving the student's skills in defining subclasses;
-   adding a new functionality to an existing class.

## Scenario

Your task is to slightly extend the `Queue` class' capabilities. We want it to have a parameterless method that returns True if the queue is empty and False otherwise.

Complete the code we've provided in the editor. Run it to check whether it outputs a similar result to ours.

Below you can copy the code we used in the previous lab:

Check

`class QueueError(IndexError): pass class Queue: def __init__(self): self.queue = [] def put(self,elem): self.queue.insert(0,elem) def get(self): if len(self.queue) > 0: elem = self.queue[-1] del self.queue[-1] return elem else: raise QueueError`

  
  

## Expected output

`1 dog False Queue empty`
```python
class QueueError(???):
    pass


class Queue:
    #
    # Code from the previous lab.
    #


class SuperQueue(Queue):
    #
    # Write new code here.
    #


que = SuperQueue()
que.put(1)
que.put("dog")
que.put(False)
for i in range(4):
    if not que.isempty():
        print(que.get())
    else:
        print("Queue empty")
```
# Instance variables

In general, a class can be equipped with two different kinds of data to form a class's properties. You already saw one of them when we were looking at stacks.

This kind of class property exists when and only when it is explicitly created and added to an object. As you already know, this can be done during the object's initialization, performed by the constructor.

Moreover, it can be done in any moment of the object's life. Furthermore, any existing property can be removed at any time.

Such an approach has some important consequences:

-   different objects of the same class **may possess different sets of properties**;
-   there must be a way to **safely check if a specific object owns the property** you want to utilize (unless you want to provoke an exception - it's always worth considering)
-   each object **carries its own set of properties** - they don't interfere with one another in any way.

Such variables (properties) are called **instance variables**.

The word _instance_ suggests that they are closely connected to the objects (which are class instances), not to the classes themselves. Let's take a closer look at them.

Here is an example:

`   class ExampleClass:  def __init__(self, val = 1):  self.first = val  def set_second(self, val):  self.second = val  example_object_1 = ExampleClass()  example_object_2 = ExampleClass(2)  example_object_2.set_second(3)  example_object_3 = ExampleClass(4)  example_object_3.third = 5  print(example_object_1.__dict__)  print(example_object_2.__dict__)  print(example_object_3.__dict__)   `  
  

  

It needs one additional explanation before we go into any more detail. Take a look at the last three lines of the code.

Python objects, when created, are gifted with a **small set of predefined properties and methods**. Each object has got them, whether you want them or not. One of them is a variable named `__dict__` (it's a dictionary).

The variable contains the names and values of all the properties (variables) the object is currently carrying. Let's make use of it to safely present an object's contents.

Let's dive into the code now:

-   the class named `ExampleClass` has a constructor, which **unconditionally creates an instance variable** named `first`, and sets it with the value passed through the first argument (from the class user's perspective) or the second argument (from the constructor's perspective); note the default value of the parameter - any trick you can do with a regular function parameter can be applied to methods, too;
  
-   the class also has a **method which creates another instance variable**, named `second`;
  
-   we've created three objects of the class `ExampleClass`, but all these instances differ:
  

-   `example_object_1` only has the property named `first`;
  
-   `example_object_2` has two properties: `first` and `second`;
  
-   `example_object_3` has been enriched with a property named `third` just on the fly, outside the class's code - this is possible and fully permissible.
  

The program's output clearly shows that our assumptions are correct - here it is:

`{'first': 1} {'second': 3, 'first': 2} {'third': 5, 'first': 4}`

**output**

There is one additional conclusion that should be stated here: **modifying an instance variable of any object has no impact on all the remaining objects**. Instance variables are perfectly isolated from each other.

# Instance variables: continued

Take a look at the modified example in the editor.

It's nearly the same as the previous one. The only difference is in the property names. We've **added two underscores (`__`)** in front of them.

As you know, such an addition makes the instance variable **private** - it becomes inaccessible from the outer world.

The actual behavior of these names is a bit more complicated, so let's run the program. This is the output:

`{'_ExampleClass__first': 1} {'_ExampleClass__first': 2, '_ExampleClass__second': 3} {'_ExampleClass__first': 4, '__third': 5}`

**output**

Can you see these strange names full of underscores? Where did they come from?

When Python sees that you want to add an instance variable to an object and you're going to do it inside any of the object's methods, it **mangles the operation** in the following way:

-   it puts a class name before your name;
-   it puts an additional underscore at the beginning.

This is why the `__first` becomes `_ExampleClass__first`.

**The name is now fully accessible from outside the class**. You can run a code like this:

`   print(example_object_1._ExampleClass__first)       `  

and you'll get a valid result with no errors or exceptions.

As you can see, making a property private is limited.

**The mangling won't work if you add a private instance variable outside the class code**. In this case, it'll behave like any other ordinary property.
```python
class ExampleClass:
    def __init__(self, val = 1):
        self.__first = val

    def set_second(self, val = 2):
        self.__second = val


example_object_1 = ExampleClass()
example_object_2 = ExampleClass(2)

example_object_2.set_second(3)

example_object_3 = ExampleClass(4)
example_object_3.__third = 5


print(example_object_1.__dict__)
print(example_object_2.__dict__)
print(example_object_3.__dict__)

```
# Class variables

A class variable is **a property which exists in just one copy and is stored outside any object**.

Note: no instance variable exists if there is no object in the class; a class variable exists in one copy even if there are no objects in the class.

Class variables are created differently to their instance siblings. The example will tell you more:

`   class ExampleClass:  counter = 0  def __init__(self, val = 1):  self.__first = val  ExampleClass.counter += 1  example_object_1 = ExampleClass()  example_object_2 = ExampleClass(2)  example_object_3 = ExampleClass(4)  print(example_object_1.__dict__, example_object_1.counter)  print(example_object_2.__dict__, example_object_2.counter)  print(example_object_3.__dict__, example_object_3.counter)   `  
  

  

Look:

-   there is an assignment in the first list of the class definition - it sets the variable named `counter` to 0; initializing the variable inside the class but outside any of its methods makes the variable a class variable;
-   accessing such a variable looks the same as accessing any instance attribute - you can see it in the constructor body; as you can see, the constructor increments the variable by one; in effect, the variable counts all the created objects.

Running the code will cause the following output:

`{'_ExampleClass__first': 1} 3 {'_ExampleClass__first': 2} 3 {'_ExampleClass__first': 4} 3`

**output**

Two important conclusions come from the example:

-   class variables **aren't shown in an object's `__dict__`** (this is natural as class variables aren't parts of an object) but you can always try to look into the variable of the same name, but at the class level - we'll show you this very soon;
-   a class variable **always presents the same value** in all class instances (objects)
# Class variables: continued

Mangling a class variable's name has the same effects as those you're already familiar with.

Look at the example in the editor. Can you guess its output?

Run the program and check if your predictions were correct. Everything works as expected, doesn't it?

```python
class ExampleClass:
    __counter = 0
    def __init__(self, val = 1):
        self.__first = val
        ExampleClass.__counter += 1


example_object_1 = ExampleClass()
example_object_2 = ExampleClass(2)
example_object_3 = ExampleClass(4)

print(example_object_1.__dict__, example_object_1._ExampleClass__counter)
print(example_object_2.__dict__, example_object_2._ExampleClass__counter)
print(example_object_3.__dict__, example_object_3._ExampleClass__counter)
```
# Class variables: continued

We told you before that class variables exist even when no class instance (object) had been created.

Now we're going to take the opportunity to show you **the difference between these two `__dict__` variables**, the one from the class and the one from the object.

Look at the code in the editor. The proof is there.

Let's take a closer look at it:

1.  We define one class named `ExampleClass`;
  
3.  The class defines one class variable named `varia`;
  
5.  The class constructor sets the variable with the parameter's value;
  
7.  Naming the variable is the most important aspect of the example because:

-   Changing the assignment to `self.varia = val` would create an instance variable of the same name as the class's one;
-   Changing the assignment to `varia = val` would operate on a method's local variable; (we strongly encourage you to test both of the above cases - this will make it easier for you to remember the difference)

9.  The first line of the off-class code prints the value of the `ExampleClass.varia` attribute; note - we use the value before the very first object of the class is instantiated.

Run the code in the editor and check its output.

As you can see, the class' `__dict__` contains much more data than its object's counterpart. Most of them are useless now - the one we want you to check carefully shows the current `varia` value.

Note that the object's `__dict__` is empty - the object has no instance variables.

```python
class ExampleClass:
    varia = 1
    def __init__(self, val):
        ExampleClass.varia = val


print(ExampleClass.__dict__)
example_object = ExampleClass(2)

print(ExampleClass.__dict__)
print(example_object.__dict__)
```
# Checking an attribute's existence

Python's attitude to object instantiation raises one important issue - in contrast to other programming languages, **you may not expect that all objects of the same class have the same sets of properties**.

Just like in the example in the editor. Look at it carefully.

The object created by the constructor can have only one of two possible attributes: `a` or `b`.

Executing the code will produce the following output:

`1 Traceback (most recent call last): File ".main.py", line 11, in print(example_object.b) AttributeError: 'ExampleClass' object has no attribute 'b'`

**output**

As you can see, accessing a non-existing object (class) attribute causes an AttributeError exception.
```python
class ExampleClass:
    def __init__(self, val):
        if val % 2 != 0:
            self.a = 1
        else:
            self.b = 1


example_object = ExampleClass(1)

print(example_object.a)
print(example_object.b)
```
# Checking an attribute's existence: continued

The try-except instruction gives you the chance to avoid issues with non-existent properties.

It's easy - look at the code in the editor.

As you can see, this action isn't very sophisticated. Essentially, we've just swept the issue under the carpet.

Fortunately, there is one more way to cope with the issue.

  

Python provides a **function which is able to safely check if any object/class contains a specified property**. The function is named `hasattr`, and expects two arguments to be passed to it:

-   the class or the object being checked;
-   the name of the property whose existence has to be reported (note: it has to be a string containing the attribute name, not the name alone)

The function returns True or False.

This is how you can utilize it:

`   class ExampleClass:  def __init__(self, val):  if val % 2 != 0:  self.a = 1  else:  self.b = 1  example_object = ExampleClass(1)  print(example_object.a)  if hasattr(example_object, 'b'):  print(example_object.b)   `

```python
class ExampleClass:
    def __init__(self, val):
        if val % 2 != 0:
            self.a = 1
        else:
            self.b = 1


example_object = ExampleClass(1)
print(example_object.a)

try:
    print(example_object.b)
except AttributeError:
    pass

```
# Checking an attribute's existence: continued

Don't forget that the `hasattr()` function can operate on classes, too. You can use it **to find out if a class variable is available**, just like here in the example in the editor.

The function returns True if the specified class contains a given attribute, and False otherwise.

Can you guess the code's output? Run it to check your guesses.

  

And one more example - look at the code below and try to predict its output:

`   class ExampleClass:  a = 1  def __init__(self):  self.b = 2  example_object = ExampleClass()  print(hasattr(example_object, 'b'))  print(hasattr(example_object, 'a'))  print(hasattr(ExampleClass, 'b'))  print(hasattr(ExampleClass, 'a'))   `  

Were you successful? Run the code to check your predictions.

Okay, we've made it to the end of this section. In the next section we're going to talk about methods, as methods drive the objects and make them active.

```python
class ExampleClass:
    attr = 1


print(hasattr(ExampleClass, 'attr'))
print(hasattr(ExampleClass, 'prop'))

```
# Key takeaways

  

1. An **instance variable** is a property whose existence depends on the creation of an object. Every object can have a different set of instance variables.

Moreover, they can be freely added to and removed from objects during their lifetime. All object instance variables are stored inside a dedicated dictionary named `__dict__`, contained in every object separately.

  

2. An instance variable can be private when its name starts with `__`, but don't forget that such a property is still accessible from outside the class using a **mangled name** constructed as `_ClassName__PrivatePropertyName`.

  

3. A **class variable** is a property which exists in exactly one copy, and doesn't need any created object to be accessible. Such variables are not shown as `__dict__` content.

All a class's class variables are stored inside a dedicated dictionary named `__dict__`, contained in every class separately.

  

4. A function named `hasattr()` can be used to determine if any object/class contains a specified property.

For example:

`   class Sample:  gamma = 0 # Class variable.  def __init__(self):  self.alpha = 1 # Instance variable.  self.__delta = 3 # Private instance variable.  obj = Sample()  obj.beta = 2 # Another instance variable (existing only inside the "obj" instance.)  print(obj.__dict__)   `  

The code outputs:

`{'alpha': 1, '_Sample__delta': 3, 'beta': 2}`

**output**

  

  

**Exercise 1**

Which of the `Python` class properties are instance variables and which are class variables? Which of them are private?  
  
`class Python: population = 1 victims = 0 def __init__(self): self.length_ft = 3 self.__venomous = False`

Check

`population` and `victims` are **class** variables, while `length` and `__venomous` are **instance** variables (the latter is also **private**).

  
  

**Exercise 2**

You're going to negate the `__venomous` property of the `version_2` object, ignoring the fact that the property is private. How will you do this?

`version_2 = Python()`  
Check

`version_2._Python__venomous = not version_2._Python__venomous`

  
  

**Exercise 3**

Write an expression which checks if the `version_2` object contains an instance property named `constrictor` (yes, constr**i**ctor!).

Check

`hasattr(version_2, 'constrictor')`

# Methods in detail

Let's summarize all the facts regarding the use of methods in Python classes.

As you already know, a **method is a function embedded inside a class**.

There is one fundamental requirement - a **method is obliged to have at least one parameter** (there are no such thing as parameterless methods - a method may be invoked without an argument, but not declared without parameters).

The first (or only) parameter is usually named `self`. We suggest that you follow the convention - it's commonly used, and you'll cause a few surprises by using other names for it.

The name self suggests the parameter's purpose - **it identifies the object for which the method is invoked**.

If you're going to invoke a method, you mustn't pass the argument for the `self` parameter - Python will set it for you.

The example in the editor shows the difference.

The code outputs:

`method`

**output**

Note the way we've created the object - we've **treated the class name like a function**, returning a newly instantiated object of the class.

---

If you want the method to accept parameters other than `self`, you should:

-   place them after `self` in the method's definition;
-   deliver them during invocation without specifying `self` (as previously)

Just like here:

`   class Classy:  def method(self, par):  print("method:", par)  obj = Classy()  obj.method(1)  obj.method(2)  obj.method(3)   `  

The code outputs:

`method: 1 method: 2 method: 3`

**output**

```python
class Classy:
    def method(self):
        print("method")


obj = Classy()
obj.method()
```
# Methods in detail: continued

The `self` parameter is used **to obtain access to the object's instance and class variables**.

The example shows both ways of utilizing `self`:

`   class Classy:  varia = 2  def method(self):  print(self.varia, self.var)  obj = Classy()  obj.var = 3  obj.method()   `  

The code outputs:

`2 3`

**output**

The `self` parameter is also used **to invoke other object/class methods from inside the class**.

Just like here:

`   class Classy:  def other(self):  print("other")  def method(self):  print("method")  self.other()  obj = Classy()  obj.method()   `  

The code outputs:

`method other`

**output**

# Methods in detail: continued

If you name a method like this: `__init__`, it won't be a regular method - it will be a **constructor**.

If a class has a constructor, it is invoked automatically and implicitly when the object of the class is instantiated.

The constructor:

-   is **obliged to have the `self` parameter** (it's set automatically, as usual);
-   **may (but doesn't need to) have more parameters** than just `self`; if this happens, the way in which the class name is used to create the object must reflect the `__init__` definition;
-   **can be used to set up the object**, i.e., properly initialize its internal state, create instance variables, instantiate any other objects if their existence is needed, etc.

Look at the code in the editor. The example shows a very simple constructor at work.

Run it. The code outputs:

`object`

**output**

Note that the constructor:

-   **cannot return a value**, as it is designed to return a newly created object and nothing else;
-   **cannot be invoked directly either from the object or from inside the class** (you can invoke a constructor from any of the object's subclasses, but we'll discuss this issue later.)
```python
class Classy:
    def __init__(self, value):
        self.var = value


obj_1 = Classy("object")

print(obj_1.var)
```
# Methods in detail: continued

As `__init__` is a method, and a method is a function, you can do the same tricks with constructors/methods as you do with ordinary functions.

The example in the editor shows how to define a constructor with a default argument value. Test it.

The code outputs:

`object None`

**output**

Everything we've said about **property name mangling** applies to method names, too - a method whose name starts with `__` is (partially) hidden.

The example shows this effect:

`   class Classy:  def visible(self):  print("visible")  def __hidden(self):  print("hidden")  obj = Classy()  obj.visible()  try:  obj.__hidden()  except:  print("failed")  obj._Classy__hidden()   `  

The code outputs:

`visible failed hidden`

**output**

Run the program, and test it.

```python
class Classy:
    def __init__(self, value = None):
        self.var = value


obj_1 = Classy("object")
obj_2 = Classy()

print(obj_1.var)
print(obj_2.var)
```
# The inner life of classes and objects

Each Python class and each Python object is pre-equipped with a set of useful attributes which can be used to examine its capabilities.

You already know one of these - it's the `__dict__` property.

Let's observe how it deals with methods - look at the code in the editor.

Run it to see what it outputs. Check the output carefully.

Find all the defined methods and attributes. Locate the context in which they exist: inside the object or inside the class.
```python
class Classy:
    varia = 1
    def __init__(self):
        self.var = 2

    def method(self):
        pass

    def __hidden(self):
        pass


obj = Classy()

print(obj.__dict__)
print(Classy.__dict__)
```
# The inner life of classes and objects: continued

`__dict__` is a dictionary. Another built-in property worth mentioning is `__name__`, which is a string.

The property contains **the name of the class**. It's nothing exciting, just a string.

Note: the `__name__` attribute is absent from the object - **it exists only inside classes**.

  

If you want to **find the class of a particular object**, you can use a function named `type()`, which is able (among other things) to find a class which has been used to instantiate any object.

Look at the code in the editor, run it, and see for yourself.

The code outputs:

`Classy Classy`

**output**

Note that a statement like this one:

`   print(obj.__name__)       `  

will cause an error.

```python
class Classy:
    pass


print(Classy.__name__)
obj = Classy()
print(type(obj).__name__)
```
# The inner life of classes and objects: continued

`__module__` is a string, too - it **stores the name of the module which contains the definition of the class**.

Let's check it - run the code in the editor.

The code outputs:

`__main__ __main__`

**output**

As you know, any module named `__main__` is actually not a module, but the **file currently being run**.

```python
class Classy:
    pass


print(Classy.__module__)
obj = Classy()
print(obj.__module__)
```
# The inner life of classes and objects: continued

`__bases__` is a tuple. The **tuple contains classes** (not class names) which are direct superclasses for the class.

The order is the same as that used inside the class definition.

We'll show you only a very basic example, as we want to highlight **how inheritance works**.

Moreover, we're going to show you how to use this attribute when we discuss the objective aspects of exceptions.

Note: **only classes have this attribute** - objects don't.

We've defined a function named `printbases()`, designed to present the tuple's contents clearly.

Look at the code in the editor. Analyze it and run it. It will output:

`( object ) ( object ) ( SuperOne SuperTwo )`

**output**

Note: **a class without explicit superclasses points to object** (a predefined Python class) as its direct ancestor.

```python
class SuperOne:
    pass


class SuperTwo:
    pass


class Sub(SuperOne, SuperTwo):
    pass


def printBases(cls):
    print('( ', end='')

    for x in cls.__bases__:
        print(x.__name__, end=' ')
    print(')')


printBases(SuperOne)
printBases(SuperTwo)
printBases(Sub)
```
# Reflection and introspection

All these means allow the Python programmer to perform two important activities specific to many objective languages. They are:

-   **introspection**, which is the ability of a program to examine the type or properties of an object at runtime;
-   **reflection**, which goes a step further, and is the ability of a program to manipulate the values, properties and/or functions of an object at runtime.

In other words, you don't have to know a complete class/object definition to manipulate the object, as the object and/or its class contain the metadata allowing you to recognize its features during program execution.

![[Pasted image 20221224113651.png]]
# Investigating classes

What can you find out about classes in Python? The answer is simple - everything.

Both reflection and introspection enable a programmer to do anything with every object, no matter where it comes from.

Analyze the the code in the editor.

The function named `incIntsI()` gets an object of any class, scans its contents in order to find all integer attributes with names starting with i, and increments them by one.

Impossible? Not at all!

This is how it works:

-   line 1: define a very simple class...
-   lines 3 through 10: ... and fill it with some attributes;
-   line 12: this is our function!
-   line 13: scan the `__dict__` attribute, looking for all attribute names;
-   line 14: if a name starts with i...
-   line 15: ... use the `getattr()` function to get its current value; note: `getattr()` takes two arguments: an object, and its property name (as a string), and returns the current attribute's value;
-   line 16: check if the value is of type integer, and use the function `isinstance()` for this purpose (we'll discuss this later);
-   line 17: if the check goes well, increment the property's value by making use of the `setattr()` function; the function takes three arguments: an object, the property name (as a string), and the property's new value.

The code outputs:

`{'a': 1, 'integer': 4, 'b': 2, 'i': 3, 'z': 5, 'ireal': 3.5} {'a': 1, 'integer': 5, 'b': 2, 'i': 4, 'z': 5, 'ireal': 3.5}`

**output**

That's all!
```python
class MyClass:
    pass


obj = MyClass()
obj.a = 1
obj.b = 2
obj.i = 3
obj.ireal = 3.5
obj.integer = 4
obj.z = 5


def incIntsI(obj):
    for name in obj.__dict__.keys():
        if name.startswith('i'):
            val = getattr(obj, name)
            if isinstance(val, int):
                setattr(obj, name, val + 1)


print(obj.__dict__)
incIntsI(obj)
print(obj.__dict__)
```
# Key takeaways

  

1. A method is a function embedded inside a class. The first (or only) parameter of each method is usually named `self`, which is designed to identify the object for which the method is invoked in order to access the object's properties or invoke its methods.

  

2. If a class contains a **constructor** (a method named `__init__`) it cannot return any value and cannot be invoked directly.

  

3. All classes (but not objects) contain a property named `__name__`, which stores the name of the class. Additionally, a property named `__module__` stores the name of the module in which the class has been declared, while the property named `__bases__` is a tuple containing a class's superclasses.

For example:

`   class Sample:  def __init__(self):  self.name = Sample.__name__  def myself(self):  print("My name is " + self.name + " living in a " + Sample.__module__)  obj = Sample()  obj.myself()   `  

The code outputs:

`My name is Sample living in a __main__`

**output**

  

  

**Exercise 1**

The declaration of the `Snake` class is given below. Enrich the class with a method named `increment()`, adding `1` to the `__victims` property.  
  
`class Snake: def __init__(self): self.victims = 0`

Check

`class Snake: def __init__(self): self.victims = 0 **def increment(self): self.victims += 1**`

  
  

**Exercise 2**

Redefine the `Snake` class constructor so that is has a parameter to initialize the `victims` field with a value passed to the object during construction.

  
Check

`class Snake: **def __init__(self, victims): self.victims = victims**`

  
  

**Exercise 3**

Can you predict the output of the following code?

`class Snake: pass class Python(Snake): pass print(Python.__name__, 'is a', Snake.__name__) print(Python.__bases__[0].__name__, 'can be', Python.__name__)`  
Check

`Python is a Snake Snake can be Python`

## Estimated time

30-60 minutes

## Level of difficulty

Easy/Medium

## Objectives

-   improving the student's skills in defining classes from scratch;
-   defining and using instance variables;
-   defining and using methods.

## Scenario

We need a class able to count seconds. Easy? Not as much as you may think as we're going to have some specific expectations.

Read them carefully as the class you're about write will be used to launch rockets carrying international missions to Mars. It's a great responsibility. We're counting on you!

Your class will be called `Timer`. Its constructor accepts three arguments representing **hours** (a value from range [0..23] - we will be using the military time), **minutes** (from range [0..59]) and **seconds** (from range [0..59]).

Zero is the default value for all of the above parameters. There is no need to perform any validation checks.

The class itself should provide the following facilities:

-   objects of the class should be "printable", i.e. they should be able to implicitly convert themselves into strings of the following form: "hh:mm:ss", with leading zeros added when any of the values is less than 10;
-   the class should be equipped with parameterless methods called `next_second()` and `previous_second()`, incrementing the time stored inside objects by +1/-1 second respectively.

Use the following hints:

-   all object's properties should be private;
-   consider writing a separate function (not method!) to format the time string.

Complete the template we've provided in the editor. Run your code and check whether the output looks the same as ours.

## Expected output

`23:59:59 00:00:00 23:59:59`

```python
class Timer:
    def __init__( ??? ):
        #
        # Write code here
        #

    def __str__(self):
        #
        # Write code here
        #

    def next_second(self):
        #
        # Write code here
        #

    def prev_second(self):
        #
        # Write code here
        #


timer = Timer(23, 59, 59)
print(timer)
timer.next_second()
print(timer)
timer.prev_second()
print(timer)
```
## Estimated time

30-60 minutes

## Level of difficulty

Easy/Medium

## Objectives

-   improving the student's skills in defining classes from scratch;
-   defining and using instance variables;
-   defining and using methods.

## Scenario

Your task is to implement a class called Weeker. Yes, your eyes don't deceive you – this name comes from the fact that objects of that class will be able to store and to manipulate the days of the week.

The class constructor accepts one argument – a string. The string represents the name of the day of the week and the only acceptable values must come from the following set:

Mon Tue Wed Thu Fri Sat Sun

Invoking the constructor with an argument from outside this set should raise the WeekDayError exception (define it yourself; don't worry, we'll talk about the objective nature of exceptions soon). The class should provide the following facilities:

-   objects of the class should be "printable", i.e. they should be able to implicitly convert themselves into strings of the same form as the constructor arguments;
-   the class should be equipped with one-parameter methods called `add_days(n)` and `subtract_days(n)`, with **n** being an integer number and updating the day of week stored inside the object in the way reflecting the change of date by the indicated number of days, forward or backward.
-   all object's properties should be private;

Complete the template we've provided in the editor and run your code and check whether your output looks the same as ours.

## Expected output

`Mon Tue Sun Sorry, I can't serve your request.`

```python
class WeekDayError(Exception):
    pass
	

class Weeker:
    #
    # Write code here.
    #

    def __init__(self, day):
        #
        # Write code here.
        #

    def __str__(self):
        #
        # Write code here.
        #

    def add_days(self, n):
        #
        # Write code here.
        #

    def subtract_days(self, n):
        #
        # Write code here.
        #


try:
    weekday = Weeker('Mon')
    print(weekday)
    weekday.add_days(15)
    print(weekday)
    weekday.subtract_days(23)
    print(weekday)
    weekday = Weeker('Monday')
except WeekDayError:
    print("Sorry, I can't serve your request.")
```
## Estimated time

30-60 minutes

## Level of difficulty

Easy/Medium

## Objectives

-   improving the student's skills in defining classes from scratch;
-   defining and using instance variables;
-   defining and using methods.

## Scenario

Let's visit a very special place - a plane with the Cartesian coordinate system (you can learn more about this concept here: [https://en.wikipedia.org/wiki/Cartesian_coordinate_system](https://en.wikipedia.org/wiki/Cartesian_coordinate_system)).

Each point located on the plane can be described as a pair of coordinates customarily called **x** and **y**. We expect that you are able to write a Python class which stores both coordinates as float numbers. Moreover, we want the objects of this class to evaluate the distances between any of the two points situated on the plane.

The task is rather easy if you employ the function named hypot() (available through the _math_ module) which evaluates the length of the hypotenuse of a right triangle (more details here: [https://en.wikipedia.org/wiki/Hypotenuse](https://en.wikipedia.org/wiki/Hypotenuse)) and here: [https://docs.python.org/3.7/library/math.html#trigonometric-functions](https://docs.python.org/3.7/library/math.html#trigonometric-functions).

This is how we imagine the class:

-   it's called `Point`;
-   its constructor accepts two arguments (**x** and **y** respectively), both default to zero;
-   all the properties should be private;
-   the class contains two parameterless methods called `getx()` and `gety()`, which return each of the two coordinates (the coordinates are stored privately, so they cannot be accessed directly from within the object);
-   the class provides a method called `distance_from_xy(x,y)`, which calculates and returns the distance between the point stored inside the object and the other point given as a pair of floats;
-   the class provides a method called `distance_from_point(point)`, which calculates the distance (like the previous method), but the other point's location is given as another Point class object;

Complete the template we've provided in the editor and run your code and check whether your output looks the same as ours.

## Expected output

`1.4142135623730951 1.4142135623730951`

```python
import math


class Point:
    def __init__(self, x=0.0, y=0.0):
        #
        # Write code here
        #

    def getx(self):
        #
        # Write code here
        #

    def gety(self):
        #
        # Write code here
        #

    def distance_from_xy(self, x, y):
        #
        # Write code here
        #

    def distance_from_point(self, point):
        #
        # Write code here
        #


point1 = Point(0, 0)
point2 = Point(1, 1)
print(point1.distance_from_point(point2))
print(point2.distance_from_xy(2, 0))
```
## Estimated time

30-60 minutes

## Level of difficulty

Medium

## Objectives

-   improving the student's skills in defining classes from scratch;
-   using composition.

## Scenario

Now we're going to embed the `Point` class (see Lab 3.4.1.14) inside another class. Also, we're going to put three points into one class, which will let us define a triangle. How can we do it?

The new class will be called `Triangle` and this is the list of our expectations:

-   the constructor accepts three arguments - all of them are objects of the `Point` class;
-   the points are stored inside the object as a private list;
-   the class provides a parameterless method called `perimeter()`, which calculates the perimeter of the triangle described by the three points; the perimeter is a sum of all legs' lengths (we mention it for the record, although we are sure that you know it perfectly yourself.)

Complete the template we've provided in the editor. Run your code and check whether the evaluated perimeter is the same as ours.

Below you can copy the `Point` class code we used in the previous lab:

Check

`class Point: def __init__(self, x=0.0, y=0.0): self.__x = x self.__y = y`

  
  

## Expected output

`3.414213562373095`

```python
import math


class Point:
    #
    # The code copied from the previous lab.
    #


class Triangle:
    def __init__(self, vertice1, vertice2, vertice3):
        #
        # Write code here
        #

    def perimeter(self):
        #
        # Write code here
        #


triangle = Triangle(Point(0, 0), Point(1, 0), Point(0, 1))
print(triangle.perimeter())
```
# Inheritance - why and how?

Before we start talking about inheritance, we want to present a new, handy mechanism utilized by Python's classes and objects - it's **the way in which the object is able to introduce itself**.

Let's start with an example. Look at the code in the editor.

The program prints out just one line of text, which in our case is this:

`<__main__.Star object at 0x7f1074cc7c50>`

**output**

If you run the same code on your computer, you'll see something very similar, although the hexadecimal number (the substring starting with 0x) will be different, as it's just an internal object identifier used by Python, and it's unlikely that it would appear the same when the same code is run in a different environment.

As you can see, the printout here isn't really useful, and something more specific, or just prettier, may be more preferable.

Fortunately, Python offers just such a function.

```python
class Star:
    def __init__(self, name, galaxy):
        self.name = name
        self.galaxy = galaxy


sun = Star("Sun", "Milky Way")
print(sun)
```
# Inheritance - why and how?

When Python needs any class/object to be presented as a string (putting an object as an argument in the `print()` function invocation fits this condition) it tries to invoke a method named `__str__()` from the object and to use the string it returns.

The default `__str__()` method returns the previous string - ugly and not very informative. You can change it just by **defining your own method of the name**.

We've just done it - look at the code in the editor.

This new `__str__()` method makes a string consisting of the star's and galaxy's names - nothing special, but the print results look better now, doesn't it?

Can you guess the output? Run the code to check if you were right.

```python
class Star:
    def __init__(self, name, galaxy):
        self.name = name
        self.galaxy = galaxy

    def __str__(self):
        return self.name + ' in ' + self.galaxy


sun = Star("Sun", "Milky Way")
print(sun)

```
# Inheritance - why and how?

The term inheritance is older than computer programming, and it describes the common practice of passing different goods from one person to another upon that person's death. The term, when related to computer programming, has an entirely different meaning.
![[Pasted image 20221224113904.png]]
  
Let's define the term for our purposes:

Inheritance is a common practice (in object programming) of **passing attributes and methods from the superclass (defined and existing) to a newly created class, called the subclass**.

In other words, inheritance is **a way of building a new class, not from scratch, but by using an already defined repertoire of traits**. The new class inherits (and this is the key) all the already existing equipment, but is able to add some new ones if needed.

Thanks to that, it's possible to **build more specialized (more concrete) classes** using some sets of predefined general rules and behaviors.

  
  

  

The most important factor of the process is the relation between the superclass and all of its subclasses (note: if _B_ is a subclass of _A_ and _C_ is a subclass of _B_, this also means than _C_ is a subclass of _A_, as the relationship is fully transitive).

A very simple example of **two-level inheritance** is presented here:

`   class Vehicle:  pass  class LandVehicle(Vehicle):  pass  class TrackedVehicle(LandVehicle):  pass       `  

All the presented classes are empty for now, as we're going to show you how the mutual relations between the super- and subclasses work. We'll fill them with contents soon.

We can say that:

-   The `Vehicle` class is the superclass for both the `LandVehicle` and `TrackedVehicle` classes;
-   The `LandVehicle` class is a subclass of `Vehicle` and a superclass of `TrackedVehicle` at the same time;
-   The `TrackedVehicle` class is a subclass of both the `Vehicle` and `LandVehicle` classes.

The above knowledge comes from reading the code (in other words, we know it because we can see it).

Does Python know the same? Is it possible to ask Python about it? Yes, it is.

# Inheritance: issubclass()

Python offers a function which is able to **identify a relationship between two classes**, and although its diagnosis isn't complex, it can **check if a particular class is a subclass of any other class**.

This is how it looks:

`   issubclass(ClassOne, ClassTwo)       `  

The function returns True if `ClassOne` is a subclass of `ClassTwo`, and False otherwise.

Let's see it in action - it may surprise you. Look at the code in the editor. Read it carefully.

There are two nested loops. Their purpose is to **check all possible ordered pairs of classes, and to print the results of the check to determine whether the pair matches the subclass-superclass relationship**.

Run the code. The program produces the following output:

`True False False True True False True True True`

**output**

Let's make the result more readable:
![[Pasted image 20221224113939.png]]
There is one important observation to make: **each class is considered to be a subclass of itself**.
```python
class Vehicle:
    pass


class LandVehicle(Vehicle):
    pass


class TrackedVehicle(LandVehicle):
    pass


for cls1 in [Vehicle, LandVehicle, TrackedVehicle]:
    for cls2 in [Vehicle, LandVehicle, TrackedVehicle]:
        print(issubclass(cls1, cls2), end="\t")
    print()
```
# Inheritance: isinstance()

As you already know, **an object is an incarnation of a class**. This means that the object is like a cake baked using a recipe which is included inside the class.

This can generate some important issues.

Let's assume that you've got a cake (e.g., as an argument passed to your function). You want to know what recipe has been used to make it. Why? Because you want to know what to expect from it, e.g., whether it contains nuts or not, which is crucial information to some people.

Similarly, it can be crucial if the object does have (or doesn't have) certain characteristics. In other words, **whether it is an object of a certain class or not**.

Such a fact could be detected by the function named `isinstance()`:

`   isinstance(objectName, ClassName)       `  

The functions returns True if the object is an instance of the class, or False otherwise.

**Being an instance of a class means that the object (the cake) has been prepared using a recipe contained in either the class or one of its superclasses**.

Don't forget: if a subclass contains at least the same equipment as any of its superclasses, it means that objects of the subclass can do the same as objects derived from the superclass, ergo, it's an instance of its home class and any of its superclasses.

Let's test it. Analyze the code in the editor.

We've created three objects, one for each of the classes. Next, using two nested loops, we check all possible object-class pairs **to find out if the objects are instances of the classes**.

Run the code.

This is what we get:

`True False False True True False True True True`

**output**

Let's make the result more readable once again:
![[Pasted image 20221224114053.png]]
Does the table confirm our expectations?
```python
class Vehicle:
    pass


class LandVehicle(Vehicle):
    pass


class TrackedVehicle(LandVehicle):
    pass


my_vehicle = Vehicle()
my_land_vehicle = LandVehicle()
my_tracked_vehicle = TrackedVehicle()

for obj in [my_vehicle, my_land_vehicle, my_tracked_vehicle]:
    for cls in [Vehicle, LandVehicle, TrackedVehicle]:
        print(isinstance(obj, cls), end="\t")
    print()
```
# Inheritance: the is operator

There is also a Python operator worth mentioning, as it refers directly to objects - here it is:

`   object_one is object_two       `  

**The `is` operator checks whether two variables (`object_one` and `object_two` here) refer to the same object**.

Don't forget that **variables don't store the objects themselves, but only the handles pointing to the internal Python memory**.

Assigning a value of an object variable to another variable doesn't copy the object, but only its handle. This is why an operator like `is` may be very useful in particular circumstances.

Take a look at the code in the editor. Let's analyze it:

-   there is a very simple class equipped with a simple constructor, creating just one property. The class is used to instantiate two objects. The former is then assigned to another variable, and its `val` property is incremented by one.
-   afterward, the `is` operator is applied three times to check all possible pairs of objects, and all `val` property values are also printed.
-   the last part of the code carries out another experiment. After three assignments, both strings contain the same texts, but **these texts are stored in different objects**.

The code prints:

`False False True 1 2 1 True False`

**output**

The results prove that `object_1` and `object_3` are actually the same objects, while `string_1` and `string_2` aren't, despite their contents being the same.
```python
class SampleClass:
    def __init__(self, val):
        self.val = val


object_1 = SampleClass(0)
object_2 = SampleClass(2)
object_3 = object_1
object_3.val += 1

print(object_1 is object_2)
print(object_2 is object_3)
print(object_3 is object_1)
print(object_1.val, object_2.val, object_3.val)

string_1 = "Mary had a little "
string_2 = "Mary had a little lamb"
string_1 += "lamb"

print(string_1 == string_2, string_1 is string_2)
```
# How Python finds properties and methods

Now we're going to look at how Python deals with inheriting methods.

Take a look at the example in the editor. Let's analyze it:

-   there is a class named `Super`, which defines its own constructor used to assign the object's property, named `name`.
-   the class defines the `__str__()` method, too, which makes the class able to present its identity in clear text form.
-   the class is next used as a base to create a subclass named `Sub`. The `Sub` class defines its own constructor, which invokes the one from the superclass. Note how we've done it: `Super.__init__(self, name)`.
-   we've explicitly named the superclass, and pointed to the method to invoke `__init__()`, providing all needed arguments.
-   we've instantiated one object of class `Sub` and printed it.

The code outputs:

`My name is Andy.`

**output**

Note: As there is no `__str__()` method within the `Sub` class, the printed string is to be produced within the `Super` class. This means that the `__str__()` method has been inherited by the `Sub` class.
```python
class Super:
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return "My name is " + self.name + "."


class Sub(Super):
    def __init__(self, name):
        Super.__init__(self, name)


obj = Sub("Andy")

print(obj)
```
# How Python finds properties and methods: continued

Look at the code in the editor. We've modified it to show you another method of accessing any entity defined inside the superclass.

In the last example, we explicitly named the superclass. In this example, we make use of the `super()` function, which **accesses the superclass without needing to know its name**:

`   super().__init__(name)       `  

The `super()` function creates a context in which you don't have to (moreover, you mustn't) pass the self argument to the method being invoked - this is why it's possible to activate the superclass constructor using only one argument.

Note: you can use this mechanism not only to **invoke the superclass constructor, but also to get access to any of the resources available inside the superclass**.
```python
class Super:
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return "My name is " + self.name + "."


class Sub(Super):
    def __init__(self, name):
        super().__init__(name)


obj = Sub("Andy")

print(obj)
```
# How Python finds properties and methods: continued

Let's try to do something similar, but with properties (more precisely: with **class variables**).

Take a look at the example in the editor.

As you can see, the `Super` class defines one class variable named `supVar`, and the `Sub` class defines a variable named `subVar`.

Both these variables are visible inside the object of class `Sub` - this is why the code outputs:

`2 1`

**output**
```python
# Testing properties: class variables.
class Super:
    supVar = 1


class Sub(Super):
    subVar = 2


obj = Sub()

print(obj.subVar)
print(obj.supVar)
```
# How Python finds properties and methods: continued

The same effect can be observed with **instance variables** - take a look at the second example in the editor.

The `Sub` class constructor creates an instance variable named `subVar`, while the `Super` constructor does the same with a variable named `supVar`. As previously, both variables are accessible from within the object of class `Sub`.

The program's output is:

`12 11`

**output**

Note: the existence of the `supVar` variable is obviously conditioned by the `Super` class constructor invocation. Omitting it would result in the absence of the variable in the created object (try it yourself).
```python
# Testing properties: instance variables.
class Super:
    def __init__(self):
        self.supVar = 11


class Sub(Super):
    def __init__(self):
        super().__init__()
        self.subVar = 12


obj = Sub()

print(obj.subVar)
print(obj.supVar)
```
# How Python finds properties and methods: continued

It's now possible to formulate a general statement describing Python's behavior.

When you try to access any object's entity, Python will try to (in this order):

-   find it **inside the object** itself;
-   find it **in all classes** involved in the object's inheritance line from bottom to top;

If both of the above fail, an **exception (`AttributeError`) is raised**.

  

The first condition may need some additional attention. As you know, all objects deriving from a particular class may have different sets of attributes, and some of the attributes may be added to the object a long time after the object's creation.

The example in the editor summarizes this in a **three-level inheritance line**. Analyze it carefully.

All the comments we've made so far are related to **single inheritance**, when a subclass has exactly one superclass. This is the most common situation (and the recommended one, too).

Python, however, offers much more here. In the next lessons we're going to show you some examples of **multiple inheritance**.
```python
class Level1:
    variable_1 = 100
    def __init__(self):
        self.var_1 = 101

    def fun_1(self):
        return 102


class Level2(Level1):
    variable_2 = 200
    def __init__(self):
        super().__init__()
        self.var_2 = 201
    
    def fun_2(self):
        return 202


class Level3(Level2):
    variable_3 = 300
    def __init__(self):
        super().__init__()
        self.var_3 = 301

    def fun_3(self):
        return 302


obj = Level3()

print(obj.variable_1, obj.var_1, obj.fun_1())
print(obj.variable_2, obj.var_2, obj.fun_2())
print(obj.variable_3, obj.var_3, obj.fun_3())

```
# How Python finds properties and methods: continued

**Multiple inheritance occurs when a class has more than one superclass**. Syntactically, such inheritance is presented as a comma-separated list of superclasses put inside parentheses after the new class name - just like here:

`class SuperA: var_a = 10 def fun_a(self): return 11 class SuperB: var_b = 20 def fun_b(self): return 21 class Sub(SuperA, SuperB): pass obj = Sub() print(obj.var_a, obj.fun_a()) print(obj.var_b, obj.fun_b())`  

The `Sub` class has two superclasses: `SuperA` and `SuperB`. This means that the `Sub` class **inherits all the goods offered by both `SuperA` and `SuperB`**.

The code prints:

`10 11 20 21`

**output**

Now it's time to introduce a brand new term - **overriding**.

What do you think will happen if more than one of the superclasses defines an entity of a particular name?
```python
class SuperA:
    var_a = 10
    def fun_a(self):
        return 11


class SuperB:
    var_b = 20
    def fun_b(self):
        return 21


class Sub(SuperA, SuperB):
    pass


obj = Sub()

print(obj.var_a, obj.fun_a())
print(obj.var_b, obj.fun_b())
```
# How Python finds properties and methods: continued

Let's analyze the example in the editor.

Both, `Level1` and `Level2` classes define a method named `fun()` and a property named `var`. Does this mean that the `Level3` class object will be able to access two copies of each entity? Not at all.

**The entity defined later (in the inheritance sense) overrides the same entity defined earlier**. This is why the code produces the following output:

`200 201`

**output**

As you can see, the `var` class variable and `fun()` method from the `Level2` class override the entities of the same names derived from the `Level1` class.

This feature can be intentionally used to modify default (or previously defined) class behaviors when any of its classes needs to act in a different way to its ancestor.

We can also say that **Python looks for an entity from bottom to top**, and is fully satisfied with the first entity of the desired name.

How does it work when a class has two ancestors offering the same entity, and they lie on the same level? In other words, what should you expect when a class emerges using multiple inheritance? Let's look at this.

```python
class Level1:
    var = 100
    def fun(self):
        return 101


class Level2(Level1):
    var = 200
    def fun(self):
        return 201


class Level3(Level2):
    pass


obj = Level3()

print(obj.var, obj.fun())
```
# How Python finds properties and methods: continued

Let's take a look at the example in the editor.

The `Sub` class inherits goods from two superclasses, `Left` and `Right` (these names are intended to be meaningful).

There is no doubt that the class variable `var_right` comes from the `Right` class, and `var_left` comes from `Left` respectively.

This is clear. But where does `var` come from? Is it possible to guess it? The same problem is encountered with the `fun()` method - will it be invoked from `Left` or from `Right`? Let's run the program - its output is:

`L LL RR Left`

**output**

This proves that both unclear cases have a solution inside the `Left` class. Is this a sufficient premise to formulate a general rule? Yes, it is.

We can say that **Python looks for object components** in the following order:

-   **inside the object** itself;
-   **in its superclasses**, from bottom to top;
-   if there is more than one class on a particular inheritance path, Python scans them from left to right.

Do you need anything more? Just make a small amendment in the code - replace: `class Sub(Left, Right):` with: `class Sub(Right, Left):`, then run the program again, and see what happens.

What do you see now? We see:

`R LL RR Right`

**output**

Do you see the same, or something different?

```python
class Left:
    var = "L"
    var_left = "LL"
    def fun(self):
        return "Left"


class Right:
    var = "R"
    var_right = "RR"
    def fun(self):
        return "Right"


class Sub(Left, Right):
    pass


obj = Sub()

print(obj.var, obj.var_left, obj.var_right, obj.fun())
```
# How to build a hierarchy of classes

Building a hierarchy of classes isn't just art for art's sake.

If you divide a problem among classes and decide which of them should be located at the top and which should be placed at the bottom of the hierarchy, you have to carefully analyze the issue, but before we show you how to do it (and how not to do it), we want to highlight an interesting effect. It's nothing extraordinary (it's just a consequence of the general rules presented earlier), but remembering it may be key to understanding how some codes work, and how the effect may be used to build a flexible set of classes.

Take a look at the code in the editor. Let's analyze it:

-   there are two classes, named `One` and `Two`, while `Two` is derived from `One`. Nothing special. However, one thing looks remarkable - the `do_it()` method.
-   the `do_it()`method is **defined twice**: originally inside `One` and subsequently inside `Two`. The essence of the example lies in the fact that it is **invoked just once** - inside `One`.

The question is - which of the two methods will be invoked by the last two lines of the code?

  

The first invocation seems to be simple, and it is simple, actually - invoking `doanything()` from the object named `one` will obviously activate the first of the methods.

The second invocation needs some attention. It's simple, too if you keep in mind how Python finds class components. The second invocation will launch `do_it()` in the form existing inside the `Two` class, regardless of the fact that the invocation takes place within the `One` class.

In effect, the code produces the following output:

`do_it from One do_it from Two`

**output**

Note: the situation in which **the subclass is able to modify its superclass behavior (just like in the example) is called polymorphism**. The word comes from Greek (polys: "many, much" and morphe, "form, shape"), which means that one and the same class can take various forms depending on the redefinitions done by any of its subclasses.

The method, redefined in any of the superclasses, thus changing the behavior of the superclass, is called **virtual**.

In other words, no class is given once and for all. Each class's behavior may be modified at any time by any of its subclasses.

We're going to show you **how to use polymorphism to extend class flexibility**.

```python
class One:
    def do_it(self):
        print("do_it from One")

    def doanything(self):
        self.do_it()


class Two(One):
    def do_it(self):
        print("do_it from Two")


one = One()
two = Two()

one.doanything()
two.doanything()
```
# How to build a hierarchy of classes: continued

Look at the example in the editor.

Does it resemble anything? Yes, of course it does. It refers to the example shown at the beginning of the module when we talked about the general concepts of objective programming.

It may look weird, but we didn't use inheritance in any way - just to show you that it doesn't limit us, and we managed to get ours.

We defined two separate classes able to produce two different kinds of land vehicles. The main difference between them is in how they turn. A wheeled vehicle just turns the front wheels (generally). A tracked vehicle has to stop one of the tracks.

Can you follow the code?

-   a tracked vehicle performs a turn by stopping and moving on one of its tracks (this is done by the `control_track()` method, which will be implemented later)
-   a wheeled vehicle turns when its front wheels turn (this is done by the `turn_front_wheels()` method)
-   the `turn()` method uses the method suitable for each particular vehicle.

Can you see **what's wrong with the code**?

The `turn()` methods look too similar to leave them in this form.

Let's rebuild the code - we're going to introduce a superclass to gather all the similar aspects of the driving vehicles, moving all the specifics to the subclasses.

```python
import time

class TrackedVehicle:
    def control_track(left, stop):
        pass

    def turn(left):
        control_track(left, True)
        time.sleep(0.25)
        control_track(left, False)


class WheeledVehicle:
    def turn_front_wheels(left, on):
        pass

    def turn(left):
        turn_front_wheels(left, True)
        time.sleep(0.25)
        turn_front_wheels(left, False)
```
# How to build a hierarchy of classes: continued

Look at the code in the editor again. This is what we've done:

-   we defined a superclass named `Vehicle`, which uses the `turn()` method to implement a general scheme of turning, while the turning itself is done by a method named `change_direction()`; note: the former method is empty, as we are going to put all the details into the subclass (such a method is often called an **abstract method**, as it only demonstrates some possibility which will be instantiated later)
-   we defined a subclass named `TrackedVehicle` (note: it's derived from the `Vehicle` class) which instantiated the `change_direction()` method by using the specific (concrete) method named `control_track()`
-   respectively, the subclass named `WheeledVehicle` does the same trick, but uses the `turn_front_wheels()` method to force the vehicle to turn.

The most important advantage (omitting readability issues) is that this form of code enables you to implement a brand new turning algorithm just by modifying the `turn()` method, which can be done in just one place, as all the vehicles will obey it.

This is how **polymorphism helps the developer to keep the code clean and consistent**.
```python
import time

class Vehicle:
    def change_direction(left, on):
        pass

    def turn(left):
        change_direction(left, True)
        time.sleep(0.25)
        change_direction(left, False)


class TrackedVehicle(Vehicle):
    def control_track(left, stop):
        pass

    def change_direction(left, on):
        control_track(left, on)


class WheeledVehicle(Vehicle):
    def turn_front_wheels(left, on):
        pass

    def change_direction(left, on):
        turn_front_wheels(left, on)
```
# How to build a hierarchy of classes: continued

Inheritance is not the only way of constructing adaptable classes. You can achieve the same goals (not always, but very often) by using a technique named composition.

**Composition is the process of composing an object using other different objects**. The objects used in the composition deliver a set of desired traits (properties and/or methods) so we can say that they act like blocks used to build a more complicated structure.

It can be said that:

-   **inheritance extends a class's capabilities** by adding new components and modifying existing ones; in other words, the complete recipe is contained inside the class itself and all its ancestors; the object takes all the class's belongings and makes use of them;
-   **composition projects a class as a container** able to store and use other objects (derived from other classes) where each of the objects implements a part of a desired class's behavior.

Let us illustrate the difference by using the previously defined vehicles. The previous approach led us to a hierarchy of classes in which the top-most class was aware of the general rules used in turning the vehicle, but didn't know how to control the appropriate components (wheels or tracks).

The subclasses implemented this ability by introducing specialized mechanisms. Let's do (almost) the same thing, but using composition. The class - like in the previous example - is aware of how to turn the vehicle, but the actual turn is done by a specialized object stored in a property named `controller`. The `controller` is able to control the vehicle by manipulating the relevant vehicle's parts.

Take a look into the editor - this is how it could look.

There are two classes named `Tracks` and `Wheels` - they know how to control the vehicle's direction. There is also a class named `Vehicle` which can use any of the available controllers (the two already defined, or any other defined in the future) - the `controller` itself is passed to the class during initialization.

In this way, the vehicle's ability to turn is composed using an external object, not implemented inside the `Vehicle` class.

In other words, we have a universal vehicle and can install either tracks or wheels onto it.

The code produces the following output:

`wheels: True True wheels: True False tracks: False True tracks: False False`

**output**
```python
import time

class Tracks:
    def change_direction(self, left, on):
        print("tracks: ", left, on)


class Wheels:
    def change_direction(self, left, on):
        print("wheels: ", left, on)


class Vehicle:
    def __init__(self, controller):
        self.controller = controller

    def turn(self, left):
        self.controller.change_direction(left, True)
        time.sleep(0.25)
        self.controller.change_direction(left, False)


wheeled = Vehicle(Wheels())
tracked = Vehicle(Tracks())

wheeled.turn(True)
tracked.turn(False)
```
# Single inheritance vs. multiple inheritance

As you already know, there are no obstacles to using multiple inheritance in Python. You can derive any new class from more than one previously defined classes.

There is only one "but". The fact that you can do it does not mean you have to.

Don't forget that:

-   a single inheritance class is always simpler, safer, and easier to understand and maintain;
  
-   multiple inheritance is always risky, as you have many more opportunities to make a mistake in identifying these parts of the superclasses which will effectively influence the new class;
  
-   multiple inheritance may make overriding extremely tricky; moreover, using the `super()` function becomes ambiguous;
  

  
  

  

-   multiple inheritance violates the **single responsibility principle** (more details here: [https://en.wikipedia.org/wiki/Single_responsibility_principle](https://en.wikipedia.org/wiki/Single_responsibility_principle)) as it makes a new class of two (or more) classes that know nothing about each other;
  
-   we strongly suggest multiple inheritance as the last of all possible solutions - if you really need the many different functionalities offered by different classes, composition may be a better alternative.
# What is Method Resolution Order (MRO) and why is it that not all inheritances make sense?

MRO, in general, is a way (you can call it a **strategy**) in which a particular programming language scans through the upper part of a class’s hierarchy in order to find the method it currently needs. It's worth emphasizing that different languages use slightly (or even completely) different MROs. Python is a unique creature in this respect, however, and its customs are a bit specific.

We're going to show you how Python's MRO works in two peculiar cases that are clear-cut examples of problems which may occur when you try to use multiple inheritance too recklessly. Let's start with a snippet that initially may look simple. Look at what we've prepared for you in the editor.

We're sure that if you analyze the snippet yourself, you won't see any anomalies in it. Yes, you're perfectly right - it looks clear and simple, and raises no concerns. If you run the code, it will produce the following, predictable output:

`bottom middle top`

**output**

  

No surprises so far. Let's make a tiny change to this code. Have a look:

`class Top:`

`def m_top(self):`

`print("top")`

`class Middle(Top):`

`def m_middle(self):`

`print("middle")`

`class Bottom(Middle, Top):`

`def m_bottom(self):`

`print("bottom")`

`object = Bottom()`

`object.m_bottom()`

`object.m_middle()`

`object.m_top()`

Can you see the difference? It's hidden in this line:

`class Bottom(Middle, Top):`

In this exotic way, we've turned a very simple code with a clear single-inheritance path into a mysterious multiple-inheritance riddle. “Is it valid?” you may ask. Yes, it is. “How is that possible?” you should ask now, and we hope that you really feel the need to ask this question.

As you can see, the order in which the two superclasses have been listed between parenthesis is compliant with the code's structure: the `Middle` class precedes the `Top` class, just like in the real inheritance path.

Despite its oddity, the sample is correct and works as expected, but it has to be stated that this notation doesn’t bring any new functionality or additional meaning.

Let's modify the code once again - now we'll swap both superclass names in the `Bottom` class definition. This is what the snippet looks like now:

`   class Top:  def m_top(self):  print("top")  class Middle(Top):  def m_middle(self):  print("middle")  class Bottom(Top, Middle):  def m_bottom(self):  print("bottom")  object = Bottom()  object.m_bottom()  object.m_middle()  object.m_top()   `

To anticipate your question, we’ll say that this amendment has spoiled the code, and it won't run anymore. What a pity. The order we tried to force (Top, Middle) is incompatible with the inheritance path which is derived from the code's structure. Python won't like it. This is what we'll see:

`TypeError: Cannot create a consistent method resolution order (MRO) for bases Top, Middle`

**output**

  

We think that the message speaks for itself. Python's MRO cannot be bent or violated, not just because that's the way Python works, but also because it’s a rule you have to obey.

```python
class Top:
    def m_top(self):
        print("top")


class Middle(Top):
    def m_middle(self):
        print("middle")


class Bottom(Middle):
    def m_bottom(self):
        print("bottom")


object = Bottom()
object.m_bottom()
object.m_middle()
object.m_top()
```
# The diamond problem

The second example of the spectrum of issues that can possibly arise from multiple inheritance is illustrated by a classic problem named the **diamond problem**. The name reflects the shape of the inheritance diagram - take a look at the picture:
![[Pasted image 20221224114735.png]]
-   There is the top-most superclass named A;
-   there are two subclasses derived from A: B and C;
-   and there is also the bottom-most subclass named D, derived from B and C (or C and B, as these two variants mean different things in Python)

Can you see the diamond there?

Have a look at the code in the editor. The same structure, but expressed in Python.

Some programming languages forbid multiple inheritance at all, and as a consequence, they won't let you build a diamond - this is the route that Java and C# have chosen to follow since their origins.

Python, however, has chosen a different route - it allows multiple inheritance, and it doesn't mind if you write and run code like the one in the editor. But don't forget about MRO - it's always in charge.

  

Let's rebuild our example from the previous page to make it more diamond-like, just like below:

`class Top:`

`def m_top(self):`

`print("top")`

`class Middle_Left(Top):`

`def m_middle(self):`

`print("middle_left")`

`class Middle_Right(Top):`

`def m_middle(self):`

`print("middle_right")`

`class Bottom(Middle_Left, Middle_Right):`

`def m_bottom(self):`

`print("bottom")`

`object = Bottom()`

`object.m_bottom()`

`object.m_middle()`

`object.m_top()`

Note: both `Middle` classes define **a method of the same name**: `m_middle()`.

It introduces a small uncertainty to our sample, although we're absolutely sure that you can answer the following key question: which of the two `m_middle()` methods will actually be invoked when the following line is executed?

`Object.m_middle()`

In other words, what will you see on the screen: `middle_left` or `middle_right`?

You don't need to hurry – think twice and keep Python's MRO in mind!

Are you ready?

Yes, you're right. The invocation will activate the `m_middle()` method, which comes from the `Middle_Left` class. The explanation is simple: the class is listed before `Middle_Right` on the `Bottom` class's inheritance list. If you want to make sure that there’s no doubt about it, try to swap these two classes on the list and check the results.

If you want to experience some more profound impressions about multiple inheritance and precious gemstones, try to modify our snippet and equip the `Upper` class with another specimen of the `m_middle()` method, and investigate its behavior carefully.

As you can see, diamonds may bring some problems into your life – both the real ones and those offered by Python.

```python
class A:
    pass


class B(A):
    pass


class C(A):
    pass


class D(B, C):
    pass


d = D()
```
# Key takeaways

  

1. A method named `__str__()` is responsible for **converting an object's contents into a (more or less) readable string**. You can redefine it if you want your object to be able to present itself in a more elegant form. For example:
```python
# Key takeaways

  

1. A method named `__str__()` is responsible for **converting an object's contents into a (more or less) readable string**. You can redefine it if you want your object to be able to present itself in a more elegant form. For example:
```
2. A function named `issubclass(Class_1, Class_2)` is able to determine if `Class_1` is a **subclass** of `Class_2`. For example:
```python
class Mouse:

pass

class LabMouse(Mouse):

pass

print(issubclass(Mouse, LabMouse), issubclass(LabMouse, Mouse)) # Prints "False True"
```
  
3. A function named `isinstance(Object, Class)` checks if an object **comes from an indicated class**. For example:
`   class Mouse:  pass  class LabMouse(Mouse):  pass  mickey = Mouse()  print(isinstance(mickey, Mouse), isinstance(mickey, LabMouse)) # Prints "True False".   `  

4. A operator called `is` checks if two variables refer to **the same object**. For example:

`   class Mouse:  pass  mickey = Mouse()  minnie = Mouse()  cloned_mickey = mickey  print(mickey is minnie, mickey is cloned_mickey) # Prints "False True".   `  

  

5. A parameterless function named `super()` returns a **reference to the nearest superclass of the class**. For example:

`   class Mouse:  def __str__(self):  return "Mouse"  class LabMouse(Mouse):  def __str__(self):  return "Laboratory " + super().__str__()  doctor_mouse = LabMouse();  print(doctor_mouse) # Prints "Laboratory Mouse".   `  

6. Methods as well as instance and class variables defined in a superclass are **automatically inherited** by their subclasses. For example:

`   class Mouse:  Population = 0  def __init__(self, name):  Mouse.Population += 1  self.name = name  def __str__(self):  return "Hi, my name is " + self.name  class LabMouse(Mouse):  pass  professor_mouse = LabMouse("Professor Mouser")  print(professor_mouse, Mouse.Population) # Prints "Hi, my name is Professor Mouser 1"   `  

7. In order to find any object/class property, Python looks for it inside:

-   the object itself;
-   all classes involved in the object's inheritance line from bottom to top;
-   if there is more than one class on a particular inheritance path, Python scans them from left to right;
-   if both of the above fail, the `AttributeError` exception is raised.

  

8. If any of the subclasses defines a method/class variable/instance variable of the same name as existing in the superclass, the new name **overrides** any of the previous instances of the name. For example:

`   class Mouse:  def __init__(self, name):  self.name = name  def __str__(self):  return "My name is " + self.name  class AncientMouse(Mouse):  def __str__(self):  return "Meum nomen est " + self.name  mus = AncientMouse("Caesar") # Prints "Meum nomen est Caesar"  print(mus)       `

# Exercises

**Scenario**

Assume that the following piece of code has been successfully executed:
```python
class Dog:
    kennel = 0
    def __init__(self, breed):
        self.breed = breed
        Dog.kennel += 1
    def __str__(self):
        return self.breed + " says: Woof!"


class SheepDog(Dog):
    def __str__(self):
        return super().__str__() + " Don't run away, Little Lamb!"


class GuardDog(Dog):
    def __str__(self):
        return super().__str__() + " Stay where you are, Mister Intruder!"


rocky = SheepDog("Collie")
luna = GuardDog("Dobermann")


```
Now answer the questions from exercises 1-4.

  

  

**Exercise 1**

What is the expected output of the following piece of code?  
  
`print(rocky) print(luna)`

Check

`Collie says: Woof! Don't run away, Little Lamb! Dobermann says: Woof! Stay where you are, Mister Intruder!`

  
  

**Exercise 2**

What is the expected output of the following piece of code?  
  
`print(issubclass(SheepDog, Dog), issubclass(SheepDog, GuardDog)) print(isinstance(rocky, GuardDog), isinstance(luna, GuardDog))`

Check

`True False False True`

  
  

**Exercise 3**

What is the expected output of the following piece of code?  
  
`print(luna is luna, rocky is luna) print(rocky.kennel)`

Check

`True False 2`

  
  

**Exercise 4**

Define a `SheepDog`'s subclass named `LowlandDog`, and equip it with an `__str__()` method overriding an inherited method of the same name. The new dog's `__str__()` method should return the string "Woof! I don't like mountains!" .

Check

`class LowlandDog(SheepDog): def __str__(self): return Dog.__str__(self) + " I don't like mountains!"`

# More about exceptions

Discussing object programming offers a very good opportunity to return to exceptions. The objective nature of Python's exceptions makes them a very flexible tool, able to fit to specific needs, even those you don't yet know about.

Before we dive into the **objective face of exceptions**, we want to show you some syntactical and semantic aspects of the way in which Python treats the try-except block, as it offers a little more than what we have presented so far.

The first feature we want discuss here is an additional, possible branch that can be placed inside (or rather, directly behind) the try-except block - it's the part of the code starting with `else` - just like in the example in the editor.

  

A code labelled in this way is executed when (and only when) no exception has been raised inside the `try:` part. We can say that exactly one branch can be executed after `try:` - either the one beginning with `except` (don't forget that there can be more than one branch of this kind) or the one starting with `else`.

Note: the `else:` branch has to be located after the last `except` branch.

The example code produces the following output:

`Everything went fine 0.5 Division failed None`

**output**

```python
def reciprocal(n):
    try:
        n = 1 / n
    except ZeroDivisionError:
        print("Division failed")
        return None
    else:
        print("Everything went fine")
        return n


print(reciprocal(2))
print(reciprocal(0))

```
# Exceptions are classes

All the previous examples were content with detecting a specific kind of exception and responding to it in an appropriate way. Now we're going to delve deeper, and look inside the exception itself.

You probably won't be surprised to learn that **exceptions are classes**. Furthermore, when an exception is raised, an object of the class is instantiated, and goes through all levels of program execution, looking for the except branch that is prepared to deal with it.

Such an object carries some useful information which can help you to precisely identify all aspects of the pending situation. To achieve that goal, Python offers a special variant of the exception clause - you can find it in the editor.

As you can see, the `except` statement is extended, and contains an additional phrase starting with the `as` keyword, followed by an identifier. The identifier is designed to catch the exception object so you can analyze its nature and draw proper conclusions.

Note: the identifier's scope covers its `except` branch, and doesn't go any further.

The example presents a very simple way of utilizing the received object - just print it out (as you can see, the output is produced by the object's `__str__()` method) and it contains a brief message describing the reason.

The same message will be printed if there is no fitting `except` block in the code, and Python is forced to handle it alone.

```python
try:
    i = int("Hello!")
except Exception as e:
    print(e)
    print(e.__str__())

```
# Exceptions are classes

All the built-in Python exceptions form a hierarchy of classes. There is no obstacle to extending it if you find it reasonable.

Look at the code in the editor.

This program dumps all predefined exception classes in the form of a tree-like printout.

As **a tree is a perfect example of a recursive data structure**, a recursion seems to be the best tool to traverse through it. The `print_exception_tree()` function takes two arguments:

-   a point inside the tree from which we start traversing the tree;
-   a nesting level (we'll use it to build a simplified drawing of the tree's branches)

Let's start from the tree's root - the root of Python's exception classes is the `BaseException` class (it's a superclass of all other exceptions).

For each of the encountered classes, perform the same set of operations:

-   print its name, taken from the `__name__` property;
-   iterate through the list of subclasses delivered by the `__subclasses__()` method, and recursively invoke the `print_exception_tree()` function, incrementing the nesting level respectively.
    
    Note how we've drawn the branches and forks. The printout isn't sorted in any way - you can try to sort it yourself, if you want a challenge. Moreover, there are some subtle inaccuracies in the way in which some branches are presented. That can be fixed, too, if you wish.
    
    This is how it looks:
    
    `BaseException +---Exception | +---TypeError | +---StopAsyncIteration | +---StopIteration | +---ImportError | | +---ModuleNotFoundError | | +---ZipImportError | +---OSError | | +---ConnectionError | | | +---BrokenPipeError | | | +---ConnectionAbortedError | | | +---ConnectionRefusedError | | | +---ConnectionResetError | | +---BlockingIOError | | +---ChildProcessError | | +---FileExistsError | | +---FileNotFoundError | | +---IsADirectoryError | | +---NotADirectoryError | | +---InterruptedError | | +---PermissionError | | +---ProcessLookupError | | +---TimeoutError | | +---UnsupportedOperation | | +---herror | | +---gaierror | | +---timeout | | +---Error | | | +---SameFileError | | +---SpecialFileError | | +---ExecError | | +---ReadError | +---EOFError | +---RuntimeError | | +---RecursionError | | +---NotImplementedError | | +---_DeadlockError | | +---BrokenBarrierError | +---NameError | | +---UnboundLocalError | +---AttributeError | +---SyntaxError | | +---IndentationError | | | +---TabError | +---LookupError | | +---IndexError | | +---KeyError | | +---CodecRegistryError | +---ValueError | | +---UnicodeError | | | +---UnicodeEncodeError | | | +---UnicodeDecodeError | | | +---UnicodeTranslateError | | +---UnsupportedOperation | +---AssertionError | +---ArithmeticError | | +---FloatingPointError | | +---OverflowError | | +---ZeroDivisionError | +---SystemError | | +---CodecRegistryError | +---ReferenceError | +---BufferError | +---MemoryError | +---Warning | | +---UserWarning | | +---DeprecationWarning | | +---PendingDeprecationWarning | | +---SyntaxWarning | | +---RuntimeWarning | | +---FutureWarning | | +---ImportWarning | | +---UnicodeWarning | | +---BytesWarning | | +---ResourceWarning | +---error | +---Verbose | +---Error | +---TokenError | +---StopTokenizing | +---Empty | +---Full | +---_OptionError | +---TclError | +---SubprocessError | | +---CalledProcessError | | +---TimeoutExpired | +---Error | | +---NoSectionError | | +---DuplicateSectionError | | +---DuplicateOptionError | | +---NoOptionError | | +---InterpolationError | | | +---InterpolationMissingOptionError | | | +---InterpolationSyntaxError | | | +---InterpolationDepthError | | +---ParsingError | | | +---MissingSectionHeaderError | +---InvalidConfigType | +---InvalidConfigSet | +---InvalidFgBg | +---InvalidTheme | +---EndOfBlock | +---BdbQuit | +---error | +---_Stop | +---PickleError | | +---PicklingError | | +---UnpicklingError | +---_GiveupOnSendfile | +---error | +---LZMAError | +---RegistryError | +---ErrorDuringImport +---GeneratorExit +---SystemExit +---KeyboardInterrupt`
    
    **output**
```python
def print_exception_tree(thisclass, nest = 0):
    if nest > 1:
        print("   |" * (nest - 1), end="")
    if nest > 0:
        print("   +---", end="")

    print(thisclass.__name__)

    for subclass in thisclass.__subclasses__():
        print_exception_tree(subclass, nest + 1)


print_exception_tree(BaseException)

```
# Detailed anatomy of exceptions

Let's take a closer look at the exception's object, as there are some really interesting elements here (we'll return to the issue soon when we consider Python's input/output base techniques, as their exception subsystem extends these objects a bit).

The `BaseException` class introduces a property named `args`. It's a **tuple designed to gather all arguments passed to the class constructor**. It is empty if the construct has been invoked without any arguments, or contains just one element when the constructor gets one argument (we don't count the `self` argument here), and so on.

We've prepared a simple function to print the `args` property in an elegant way. You can see the function in the editor.

  

We've used the function to print the contents of the `args` property in three different cases, where the exception of the `Exception` class is raised in three different ways. To make it more spectacular, we've also printed the object itself, along with the result of the `__str__()` invocation.

The first case looks routine - there is just the name Exception after the `raise` keyword. This means that the object of this class has been created in a most routine way.

The second and third cases may look a bit weird at first glance, but there's nothing odd here - these are just the constructor invocations. In the second `raise` statement, the constructor is invoked with one argument, and in the third, with two.

As you can see, the program output reflects this, showing the appropriate contents of the `args` property:

`: : my exception : my exception : my exception ('my', 'exception') : ('my', 'exception') : ('my', 'exception')`

**output**

```python
def print_args(args):
    lng = len(args)
    if lng == 0:
        print("")
    elif lng == 1:
        print(args[0])
    else:
        print(str(args))


try:
    raise Exception
except Exception as e:
    print(e, e.__str__(), sep=' : ' ,end=' : ')
    print_args(e.args)

try:
    raise Exception("my exception")
except Exception as e:
    print(e, e.__str__(), sep=' : ', end=' : ')
    print_args(e.args)

try:
    raise Exception("my", "exception")
except Exception as e:
    print(e, e.__str__(), sep=' : ', end=' : ')
    print_args(e.args)

```
# How to create your own exception

The exceptions hierarchy is neither closed nor finished, and you can always extend it if you want or need to create your own world populated with your own exceptions.

It may be useful when you create a complex module which detects errors and raises exceptions, and you want the exceptions to be easily distinguishable from any others brought by Python.

This is done by **defining your own, new exceptions as subclasses derived from predefined ones**.

Note: if you want to create an exception which will be utilized as a specialized case of any built-in exception, derive it from just this one. If you want to build your own hierarchy, and don't want it to be closely connected to Python's exception tree, derive it from any of the top exception classes, like Exception.

Imagine that you've created a brand new arithmetic, ruled by your own laws and theorems. It's clear that division has been redefined, too, and has to behave in a different way than routine dividing. It's also clear that this new division should raise its own exception, different from the built-in ZeroDivisionError, but it's reasonable to assume that in some circumstances, you (or your arithmetic's user) may want to treat all zero divisions in the same way.

Demands like these may be fulfilled in the way presented in the editor. Look at the code, and let's analyze it:

-   We've defined our own exception, named `MyZeroDivisionError`, derived from the built-in `ZeroDivisionError`. As you can see, we've decided not to add any new components to the class.  
      
    In effect, an exception of this class can be - depending on the desired point of view - treated like a plain ZeroDivisionError, or considered separately.
  
-   The `do_the_division()` function raises either a `MyZeroDivisionError` or `ZeroDivisionError` exception, depending on the argument's value.  
      
    The function is invoked four times in total, while the first two invocations are handled using only one `except` branch (the more general one) and the last two ones with two different branches, able to distinguish the exceptions (don't forget: the order of the branches makes a fundamental difference!)
```python
class MyZeroDivisionError(ZeroDivisionError):	
    pass


def do_the_division(mine):
    if mine:
        raise MyZeroDivisionError("some worse news")
    else:		
        raise ZeroDivisionError("some bad news")


for mode in [False, True]:
    try:
        do_the_division(mode)
    except ZeroDivisionError:
        print('Division by zero')

for mode in [False, True]:
    try:
        do_the_division(mode)
    except MyZeroDivisionError:
        print('My division by zero')
    except ZeroDivisionError:
        print('Original division by zero')

```
# How to create your own exception: continued

When you're going to build a completely new universe filled with completely new creatures that have nothing in common with all the familiar things, you may want to **build your own exception structure**.

For example, if you work on a large simulation system which is intended to model the activities of a pizza restaurant, it can be desirable to form a separate hierarchy of exceptions.

You can start building it by **defining a general exception as a new base class** for any other specialized exception. We've done in in the following way:

`   class PizzaError(Exception):  def __init__(self, pizza, message):  Exception.__init__(self, message)  self.pizza = pizza   `  

Note: we're going to collect more specific information here than a regular Exception does, so our constructor will take two arguments:

-   one specifying a pizza as a subject of the process,
-   and one containing a more or less precise description of the problem.

As you can see, we pass the second parameter to the superclass constructor, and save the first inside our own property.

A more specific problem (like an excess of cheese) can require a more specific exception. It's possible to derive the new class from the already defined `PizzaError` class, like we've done here:

`   class TooMuchCheeseError(PizzaError):  def __init__(self, pizza, cheese, message):  PizzaError._init__(self, pizza, message)  self.cheese = cheese   `  

The `TooMuchCheeseError` exception needs more information than the regular `PizzaError` exception, so we add it to the constructor - the name `cheese` is then stored for further processing.

```python
class PizzaError(Exception):
    def __init__(self, pizza, message):
        Exception.__init__(self, message)
        self.pizza = pizza


class TooMuchCheeseError(PizzaError):
    def __init__(self, pizza, cheese, message):
        PizzaError._init__(self, pizza, message)
        self.cheese = cheese

```
# How to create your own exception: continued

Look at the code in the editor. We've coupled together the two previously defined exceptions and harnessed them to work in a small example snippet.

One of these is raised inside the `make_pizza()` function when any of these two erroneous situations is discovered: a wrong pizza request, or a request for too much cheese.

Note:

-   removing the branch starting with `except TooMuchCheeseError` will cause all appearing exceptions to be classified as `PizzaError`;
-   removing the branch starting with `except PizzaErrorwill` cause the `TooMuchCheeseError` exceptions to remain unhandled, and will cause the program to terminate.

  

The previous solution, although elegant and efficient, has one important weakness. Due to the somewhat easygoing way of declaring the constructors, the new exceptions cannot be used as-is, without a full list of required arguments.

We'll remove this weakness by **setting the default values for all constructor parameters**. Take a look:
```python
class PizzaError(Exception):
    def __init__(self, pizza='uknown', message=''):
        Exception.__init__(self, message)
        self.pizza = pizza


class TooMuchCheeseError(PizzaError):
    def __init__(self, pizza='uknown', cheese='>100', message=''):
        PizzaError.__init__(self, pizza, message)
        self.cheese = cheese


def make_pizza(pizza, cheese):
    if pizza not in ['margherita', 'capricciosa', 'calzone']:
        raise PizzaError
    if cheese > 100:
        raise TooMuchCheeseError
    print("Pizza ready!")


for (pz, ch) in [('calzone', 0), ('margherita', 110), ('mafia', 20)]:
    try:
        make_pizza(pz, ch)
    except TooMuchCheeseError as tmce:
        print(tmce, ':', tmce.cheese)
    except PizzaError as pe:
        print(pe, ':', pe.pizza)


```
Now, if the circumstances permit, it is possible to use the class names alone.
```python
class PizzaError(Exception):
    def __init__(self, pizza, message):
        Exception.__init__(self, message)
        self.pizza = pizza


class TooMuchCheeseError(PizzaError):
    def __init__(self, pizza, cheese, message):
        PizzaError.__init__(self, pizza, message)
        self.cheese = cheese


def make_pizza(pizza, cheese):
    if pizza not in ['margherita', 'capricciosa', 'calzone']:
        raise PizzaError(pizza, "no such pizza on the menu")
    if cheese > 100:
        raise TooMuchCheeseError(pizza, cheese, "too much cheese")
    print("Pizza ready!")

for (pz, ch) in [('calzone', 0), ('margherita', 110), ('mafia', 20)]:
    try:
        make_pizza(pz, ch)
    except TooMuchCheeseError as tmce:
        print(tmce, ':', tmce.cheese)
    except PizzaError as pe:
        print(pe, ':', pe.pizza)

```
# Key takeaways

  

1. The `else:` branch of the `try` statement is executed when there has been no exception during the execution of the `try:` block.

  

2. The `finally:` branch of the `try` statement is **always** executed.

  

3. The syntax `except _Exception_Name_ as an _exception_object_:` lets you intercept an object carrying information about a pending exception. The object's property named `args` (a tuple) stores all arguments passed to the object's constructor.

  

4. The exception classes can be extended to enrich them with new capabilities, or to adopt their traits to newly defined exceptions.

For example:

`   try:  assert __name__ == "__main__"  except:  print("fail", end=' ')  else:  print("success", end=' ')  finally:  print("done")   `  

The code outputs: `success done`.

  

**Exercise 1**

What is the expected output of the following code?

`import math try: print(math.sqrt(9)) except ValueError: print("inf") else: print("fine")`
Check

`3.0 fine`

  
  

**Exercise 2**

What is the expected output of the following code?

`import math try: print(math.sqrt(-9)) except ValueError: print("inf") else: print("fine") finally: print("the end")`  
Check

`inf the end`

  
  

**Exercise 3**

What is the expected output of the following code?

`import math class NewValueError(ValueError): def __init__(self, name, color, state): self.data = (name, color, state) try: raise NewValueError("Enemy warning", "Red alert", "High readiness") except NewValueError as nve: for arg in nve.args: print(arg, end='! ')`  
Check

`Enemy warning! Red alert! High readiness!`

