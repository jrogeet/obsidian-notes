# Python Essentials 2:  
Module 2

**Strings, String and List Methods, Exceptions**

In this module, you will learn about:

-   Characters, strings and coding standards;
-   Strings vs. lists – similarities and differences;
-   Lists methods;
-   String methods;
-   Python's way of handling runtime errors;
-   Controlling the flow of errors using `try` and `except`;
-   Hierarchy of exceptions.
![[Pasted image 20221224104208.png]]
# How computers understand single characters

You've written some interesting programs since you've started this course, but all of them have processed only one kind of data - numbers. As you know (you can see this everywhere around you) lots of computer data are not numbers: first names, last names, addresses, titles, poems, scientific papers, emails, court judgements, love confessions, and much, much more.

![[Pasted image 20221224104222.png]]
All these data must be stored, input, output, searched, and transformed by contemporary computers just like any other data, no matter if they are single characters or multi-volume encyclopedias.

How is it possible?

How can you do it in Python? This is what we'll discuss now. Let's start with how computers understand single characters.

  

**Computers store characters as numbers**. Every character used by a computer corresponds to a unique number, and vice versa. This assignment must include more characters than you might expect. Many of them are invisible to humans, but essential to computers.

Some of these characters are called **whitespaces**, while others are named **control characters**, because their purpose is to control input/output devices.

An example of a whitespace that is completely invisible to the naked eye is a special code, or a pair of codes (different operating systems may treat this issue differently), which are used to mark the ends of the lines inside text files.

People do not see this sign (or these signs), but are able to observe the effect of their application where the lines are broken.

We can create virtually any number of character-number assignments, but life in a world in which every type of computer uses a different character encoding would not be very convenient. This system has led to a need to introduce a universal and widely accepted standard implemented by (almost) all computers and operating systems all over the world.

  
  

  

The one named **ASCII** (short for **American Standard Code for Information Interchange**) is the most widely used, and you can assume that nearly all modern devices (like computers, printers, mobile phones, tablets, etc.) use that code.

The code provides space for **256 different characters**, but we are interested only in the first 128. If you want to see how the code is constructed, look at the table below. Click the table to enlarge it. Look at it carefully - there are some interesting facts. Look at the code of the most common character - the _space_. This is _32_.

![[Pasted image 20221224104308.png]]
Now check the code of the lower-case letter _a_. This is _97_. And now find the upper-case _A_. Its code is _65_. Now work out the difference between the code of _a_ and _A_. It is equal to _32_. That's the code of a _space_. Interesting, isn't it?

Also note that the letters are arranged in the same order as in the Latin alphabet.

# I18N

Of course, the Latin alphabet is not sufficient for the whole of mankind. Users of that alphabet are in the minority. It was necessary to come up with something more flexible and capacious than ASCII, something able to make all the software in the world amenable to **internationalization**, because different languages use completely different alphabets, and sometimes these alphabets are not as simple as the Latin one.

The word _internationalization_ is commonly shortened to **I18N**.

![[Pasted image 20221224104331.png]]
Why? Look carefully - there is an _I_ at the front of the word, next there are _18_ different letters, and an _N_ at the end.

Despite the slightly humorous origin, the term is officially used in many documents and standards.

The **software I18N** is a standard in present times. Each program has to be written in a way that enables it to be used all around the world, among different cultures, languages and alphabets.

**A classic form of ASCII code uses eight bits for each sign**. Eight bits mean 256 different characters. The first 128 are used for the standard Latin alphabet (both upper-case and lower-case characters). Is it possible to push all the other national characters used around the world into the remaining 128 locations?

No. It isn't.

  
  

## Code points and code pages

We need a new term now: a **code point**.

A code point is **a number which makes a character**. For example, _32_ is a code point which makes a _space_ in ASCII encoding. We can say that standard ASCII code consists of 128 code points.

As standard ASCII occupies 128 out of 256 possible code points, you can only make use of the remaining 128.

It's not enough for all possible languages, but it may be sufficient for one language, or for a small group of similar languages.

Can you **set the higher half of the code points differently for different languages**? Yes, you can. Such a concept is called a **code page**.

A code page is a **standard for using the upper 128 code points to store specific national characters**. For example, there are different code pages for Western Europe and Eastern Europe, Cyrillic and Greek alphabets, Arabic and Hebrew languages, and so on.

This means that the one and same code point can make different characters when used in different code pages.

For example, the code point _200_ makes Č (a letter used by some Slavic languages) when utilized by the ISO/IEC 8859-2 code page, and makes Ш (a Cyrillic letter) when used by the ISO/IEC 8859-5 code page.

In consequence, to determine the meaning of a specific code point, you have to know the target code page.

In other words, the code points derived from the code page concept are ambiguous.

# Unicode

Code pages helped the computer industry to solve I18N issues for some time, but it soon turned out that they would not be a permanent solution.

The concept that solved the problem in the long term was **Unicode**.

![[Pasted image 20221224104349.png]]
**Unicode assigns unique (unambiguous) characters (letters, hyphens, ideograms, etc.) to more than a million code points**. The first 128 Unicode code points are identical to ASCII, and the first 256 Unicode code points are identical to the ISO/IEC 8859-1 code page (a code page designed for western European languages).

## UCS-4

The Unicode standard says nothing about how to code and store the characters in the memory and files. It only names all available characters and assigns them to planes (a group of characters of similar origin, application, or nature).

![[Pasted image 20221224104402.png]]
There is more than one standard describing the techniques used to implement Unicode in actual computers and computer storage systems. The most general of them is **UCS-4**.

The name comes from **Universal Character Set**.

**UCS-4 uses 32 bits (four bytes) to store each character**, and the code is just the Unicode code points' unique number. A file containing UCS-4 encoded text may start with a BOM (byte order mark), an unprintable combination of bits announcing the nature of the file's contents. Some utilities may require it.

  
  

  

As you can see, UCS-4 is a rather wasteful standard - it increases a text's size by four times compared to standard ASCII. Fortunately, there are smarter forms of encoding Unicode texts.

## UTF-8

One of the most commonly used is **UTF-8**.

The name is derived from **Unicode Transformation Format**.

The concept is very smart. **UTF-8 uses as many bits for each of the code points as it really needs to represent them**.

![[Pasted image 20221224104417.png]]
For example:

-   all Latin characters (and all standard ASCII characters) occupy eight bits;
-   non-Latin characters occupy 16 bits;
-   CJK (China-Japan-Korea) ideographs occupy 24 bits.

Due to features of the method used by UTF-8 to store the code points, there is no need to use the BOM, but some of the tools look for it when reading the file, and many editors set it up during the save.

Python 3 fully supports Unicode and UTF-8:

-   you can use Unicode/UTF-8 encoded characters to name variables and other entities;
-   you can use them during all input and output.

This means that Python3 is completely I18Ned.

# Key takeaways

  

1. Computers store characters as numbers. There is more than one possible way of encoding characters, but only some of them gained worldwide popularity and are commonly used in IT: these are **ASCII** (used mainly to encode the Latin alphabet and some of its derivates) and **UNICODE** (able to encode virtually all alphabets being used by humans).

  

2. A number corresponding to a particular character is called a **codepoint**.

  

3. UNICODE uses different ways of encoding when it comes to storing the characters using files or computer memory: two of them are **UCS-4** and **UTF-8** (the latter is the most common as it wastes less memory space).

  

**Exercise 1**

What is BOM?

Check  

**BOM** (Byte Order Mark) is a special combination of bits announcing encoding used by a file's content (eg. UCS-4 or UTF-B).

  

**Exercise 2**

Is Python 3 _I18N_ed?

Check

Yes, it's completely internationalized - we can use UNICODE characters inside our code, read them from input and send to output.

# Strings - a brief review

Let's do a brief review of the nature of Python's strings.

First of all, Python's strings (or simply strings, as we're not going to discuss any other language's strings) are **immutable sequences**.

It's very important to note this, because it means that you should expect some familiar behavior from them.

Let's analyze the code in the editor to understand what we're talking about:

-   Take a look at **Example 1**. The `len()` function used for strings returns a number of characters contained by the arguments. The snippet outputs `2`.
-   Any string can be empty. Its length is `0` then - just like in **Example 2**.
-   Don't forget that a backslash (`\`) used as an escape character is not included in the string's total length. The code in **Example 3**, therefore, outputs `3`.

Run the three example codes and check.

```python
# Example 1

word = 'by'
print(len(word))


# Example 2

empty = ''
print(len(empty))


# Example 3

i_am = 'I\'m'
print(len(i_am))

```
# Multiline strings

Now is a very good moment to show you another way of specifying strings inside the Python source code. Note that the syntax you already know won't let you use a string occupying more than one line of text.

For this reason, the code here is erroneous:

`multiline = 'Line #1 Line #2' print(len(multiline))`  

Fortunately, for these kinds of strings, Python offers separate, convenient, and simple syntax.

  

Look at the code in the editor. This is what it looks like.

As you can see, the string starts with **three apostrophes**, not one. The same tripled apostrophe is used to terminate it.

The number of text lines put inside such a string is arbitrary.

The snippet outputs `15`.

Count the characters carefully. Is this result correct or not? It looks okay at first glance, but when you count the characters, it doesn't.

`Line #1` contains seven characters. Two such lines comprise 14 characters. Did we lose a character? Where? How?

No, we didn't.

**The missing character is simply invisible - it's a whitespace**. It's located between the two text lines.

It's denoted as: `\n`.

Do you remember? It's a special (control) character used to **force a line feed** (hence its name: LF). You can't see it, but it counts.

The multiline strings can be delimited by **triple quotes**, too, just like here:

`   multiline = """Line #1  Line #2"""  print(len(multiline))       `  

Choose the method that is more comfortable for you. Both work the same.

```python
multiline = '''Line #1
Line #2'''

print(len(multiline))
```
# Operations on strings

Like other kinds of data, strings have their own set of permissible operations, although they're rather limited compared to numbers.

In general, strings can be:

-   **concatenated** (joined)
-   **replicated**.

The first operation is performed by the `+` operator (note: it's not an addition) while the second by the `*` operator (note again: it's not a multiplication).

The ability to use the same operator against completely different kinds of data (like numbers vs. strings) is called **overloading** (as such an operator is overloaded with different duties).

Analyze the example:

-   The `+` operator used against two or more strings produces a new string containing all the characters from its arguments (note: the order matters - this overloaded `+`, in contrast to its numerical version, is **not commutative**)
-   the `*` operator needs a string and a number as arguments; in this case, the order doesn't matter - you can put the number before the string, or vice versa, the result will be the same - a new string created by the nth replication of the argument's string.

The snippet produces the following output:

`ab ba aaaaa bbbb`

**output**

  

Note: shortcut variants of the above operators are also applicable for strings (`+=` and `*=`).

```python
str1 = 'a'
str2 = 'b'

print(str1 + str2)
print(str2 + str1)
print(5 * 'a')
print('b' * 4)

```
# Operations on strings: ord()

If you want **to know a specific character's ASCII/UNICODE code point value**, you can use a function named `ord()` (as in _ordinal_).

The function needs a **one-character string as its argument** - breaching this requirement causes a TypeError exception, and returns a number representing the argument's code point.

Look at the code in the editor, and run it. The snippet outputs:

`97 32`

**output**

Now assign different values to `char_1` and `char_2`, e.g., `α` (Greek alpha), and `ę` (a letter in the Polish alphabet); then run the code and see what result it outputs. Carry out your own experiments.
```python
# Demonstrating the ord() function.

char_1 = 'a'
char_2 = ' '  # space

print(ord(char_1))
print(ord(char_2))

```
# Operations on strings: chr()

If you know the code point (number) and want to get the corresponding character, you can use a function named `chr()`.

The function **takes a code point and returns its character**.

Invoking it with an invalid argument (e.g., a negative or invalid code point) causes ValueError or TypeError exceptions.

Run the code in the editor. The example snippet outputs:

`a α`

**output**

Note:

-   `chr(ord(x)) == x`
-   `ord(chr(x)) == x`

Again, run your own experiments.

```python
# Demonstrating the chr() function.

print(chr(97))
print(chr(945))

```
# Strings as sequences: indexing

We told you before that **Python strings are sequences**. It's time to show you what that actually means.

Strings aren't lists, but **you can treat them like lists in many particular cases**.

For example, if you want to access any of a string's characters, you can do it using **indexing**, just like in the example below. Run the program:

`# Indexing strings.`

`the_string = 'silly walks'`

`for ix in range(len(the_string)):`

`print(the_string[ix], end=' ')`

`print()`

Be careful - don't try to pass a string's boundaries - it will cause an exception.

The example output is:

`s i l l y w a l k s`

**output**

By the way, negative indices behave as expected, too. Check this yourself.

  

## Strings as sequences: iterating

**Iterating through the strings** works, too. Look at the example below:

`   # Iterating through a string.  the_string = 'silly walks'  for character in the_string:  print(character, end=' ')  print()   `  

The output is the same as previously. Check.

# Slices

Moreover, everything you know about **slices** is still usable.

We've gathered some examples showing how slices work in the string world. Look at the code in the editor, analyze it, and run it.

You won't see anything new in the example, but we want you to be sure that you can explain all the lines of the code.

The code's output is:

`bd efg abd e e adf beg`

**output**

Now do your own experiments.

```python
# Slices

alpha = "abdefg"

print(alpha[1:3])
print(alpha[3:])
print(alpha[:3])
print(alpha[3:-2])
print(alpha[-3:4])
print(alpha[::2])
print(alpha[1::2])

```
# The in and not in operators

**The in operator**

The `in` operator shouldn't surprise you when applied to strings - it simply **checks if its left argument (a string) can be found anywhere within the right argument (another string)**.

The result of the check is simply `True` or `False`.

Look at the example program below. This is how the `in` operator works:

`alphabet = "abcdefghijklmnopqrstuvwxyz"`

`print("f" in alphabet)`

`print("F" in alphabet)`

`print("1" in alphabet)`

`print("ghi" in alphabet)`

`print("Xyz" in alphabet)`

The example output is:

`True False False True False`

**output**

**The not in operator**

As you probably suspect, the `not in` operator is also applicable here.

This is how it works:

`   alphabet = "abcdefghijklmnopqrstuvwxyz"  print("f" not in alphabet)  print("F" not in alphabet)  print("1" not in alphabet)  print("ghi" not in alphabet)  print("Xyz" not in alphabet)   `  

The example output is:

`False True True False True`

-     
    

# Python strings are immutable

We've also told you that Python's **strings are immutable**. This is a very important feature. What does it mean?

This primarily means that the similarity of strings and lists is limited. Not everything you can do with a list may be done with a string.

The first important difference **doesn't allow you to use the `del` instruction to remove anything from a string**.

The example here won't work:

`alphabet = "abcdefghijklmnopqrstuvwxyz" del alphabet[0]`  

The only thing you can do with `del` and a string is to **remove the string as a whole**. Try to do it.

  

Python strings **don't have the `append()` method** - you cannot expand them in any way.

The example below is erroneous:

`alphabet = "abcdefghijklmnopqrstuvwxyz" alphabet.append("A")`  

with the absence of the `append()` method, **the `insert()` method is illegal**, too:

`alphabet = "abcdefghijklmnopqrstuvwxyz" alphabet.insert(0, "A")`

```python
alphabet = "abcdefghijklmnopqrstuvwxyz"

# Write test code here.

```
# Operations on strings: continued

Don't think that a string's immutability limits your ability to operate with strings.

The only consequence is that you have to remember about it, and implement your code in a slightly different way - look at the example code in the editor.

This form of code is fully acceptable, will work without bending Python's rules, and will bring the full Latin alphabet to your screen:

`abcdefghijklmnopqrstuvwxyz`

**output**

You may want to ask if **creating a new copy of a string each time you modify its contents worsens the effectiveness of the code**.

Yes, it does. A bit. It's not a problem at all, though.

```python
alphabet = "bcdefghijklmnopqrstuvwxy"

alphabet = "a" + alphabet
alphabet = alphabet + "z"

print(alphabet)

```
# Operations on strings: min()

Now that you understand that strings are sequences, we can show you some less obvious sequence capabilities. We'll present them using strings, but don't forget that lists can adopt the same tricks, too.

Let's start with a function named `min()`.

The function **finds the minimum element of the sequence passed as an argument**. There is one condition - the sequence (string, list, it doesn't matter) **cannot be empty**, or else you'll get a ValueError exception.

The **Example 1** program outputs:

`A`

**output**

  

Note: It's an upper-case _A_. Why? Recall the ASCII table - which letters occupy first locations - upper or lower?

We've prepared two more examples to analyze: **Examples 2 & 3**.

As you can see, they present more than just strings. The expected output looks as follows:

`[ ] 0`

**output**

Note: we've used the square brackets to prevent the space from being overlooked on your screen.

```python
# Demonstrating min() - Example 1:
print(min("aAbByYzZ"))


# Demonstrating min() - Examples 2 & 3:
t = 'The Knights Who Say "Ni!"'
print('[' + min(t) + ']')

t = [0, 1, 2]
print(min(t))

```

# Operations on strings: max()

Similarly, a function named `max()` **finds the maximum element of the sequence**.

Look at **Example 1** in the editor. The example program outputs:

`z`

**output**

Note: It's a lower-case _z_.

Now let's see the `max()` function applied to the same data as previously. Look at **Examples 2 & 3** in the editor.

The expected output is:

`[y] 2`

**output**

Carry out your own experiments.

```python
# Demonstrating max() - Example 1:
print(max("aAbByYzZ"))


# Demonstrating max() - Examples 2 & 3:
t = 'The Knights Who Say "Ni!"'
print('[' + max(t) + ']')

t = [0, 1, 2]
print(max(t))

```
# Operations on strings: the index() method

The `index()` method (it's a method, not a function) **searches the sequence from the beginning, in order to find the first element of the value specified in its argument**.

Note: the element searched for must occur in the sequence - **its absence will cause a ValueError exception**.

The method returns the **index of the first occurrence of the argument** (which means that the lowest possible result is 0, while the highest is the length of argument decremented by 1).

Therefore, the example in the editor outputs:

`2 7 1`

```python
# Demonstrating the index() method:
print("aAbByYzZaA".index("b"))
print("aAbByYzZaA".index("Z"))
print("aAbByYzZaA".index("A"))

```
# Operations on strings: the list() function

The `list()` function **takes its argument (a string) and creates a new list containing all the string's characters, one per list element**.

Note: it's not strictly a string function - `list()` is able to create a new list from many other entities (e.g., from tuples and dictionaries).

Take a look at the code example in the editor.

The example outputs:

`['a', 'b', 'c', 'a', 'b', 'c']`

**output**

## Operations on strings: the count() method

The `count()` method **counts all occurrences of the element inside the sequence**. The absence of such elements doesn't cause any problems.

Look at the second example in the editor. Can you guess its output?

It is:

`2 0`

**output**

Moreover, Python strings have a significant number of methods intended exclusively for processing characters. Don't expect them to work with any other collections. The complete list of is presented here: [https://docs.python.org/3.4/library/stdtypes.html#string-methods](https://docs.python.org/3.4/library/stdtypes.html#string-methods).

We're going to show you the ones we consider the most useful.

```python
# Demonstrating the list() function:
print(list("abcabc"))

# Demonstrating the count() method:
print("abcabc".count("b"))
print('abcabc'.count("d"))

```
# Key takeaways

  

1. Python strings are **immutable sequences** and can be indexed, sliced, and iterated like any other sequence, as well as being subject to the `in` and `not in` operators. There are two kinds of strings in Python:

-   **one-line** strings, which cannot cross line boundaries – we denote them using either apostrophes (`'string'`) or quotes (`"string"`)
-   **multi-line** strings, which occupy more than one line of source code, delimited by trigraphs:  
      
    `   '''  string  '''       `  
    
    or
    
    `   """  string  """       `

  

2. The length of a string is determined by the `len()` function. The escape character (`\`) is not counted. For example:

`   print(len("\n\n"))   `  

outputs `2`.

  

3. Strings can be **concatenated** using the `+` operator, and **replicated** using the `*` operator. For example:

`   asterisk = '*'  plus = "+"  decoration = (asterisk + plus) * 4 + asterisk  print(decoration)       `  

outputs `*+*+*+*+*`.

  

4. The pair of functions `chr()` and `ord()` can be used to create a character using its codepoint, and to determine a codepoint corresponding to a character. Both of the following expressions are always true:

`   chr(ord(character)) == character  ord(chr(codepoint)) == codepoint   `  

5. Some other functions that can be applied to strings are:

-   `list()` – create a list consisting of all the string's characters;
-   `max()` – finds the character with the maximal codepoint;
-   `min()` – finds the character with the minimal codepoint.

  

6. The method named `index()` finds the index of a given substring inside the string.

  

**Exercise 1**

What is the length of the following string assuming there is no whitespaces between the quotes?

`""" """`  
Check

1

  
  

**Exercise 2**

What is the expected output of the following code?

`s = 'yesteryears' the_list = list(s) print(the_list[3:6])`  
Check

`['t', 'e', 'r']`

  
  

**Exercise 3**

What is the expected output of the following code?

`for ch in "abc": print(chr(ord(ch) + 1), end='')`  
Check

`bcd`

# The capitalize() method

Let's go through some standard Python string methods. We're going to go through them in alphabetical order - to be honest, any order has as many disadvantages as advantages, so the choice may as well be random.

The `capitalize()` method does exactly what it says - **it creates a new string filled with characters taken from the source string**, but it tries to modify them in the following way:

-   **if the first character inside the string is a letter** (note: the first character is an element with an index equal to 0, not just the first visible character), **it will be converted to upper-case**;
-   **all remaining letters from the string will be converted to lower-case**.

Don't forget that:

-   the original string (from which the method is invoked) is not changed in any way (a string's immutability must be obeyed without reservation)
-   the modified (capitalized in this case) string is returned as a result - if you don't use it in any way (assign it to a variable, or pass it to a function/method) it will disappear without a trace.

Note: methods don't have to be invoked from within variables only. They can be invoked directly from within string literals. We're going to use that convention regularly - it will simplify the examples, as the most important aspects will not disappear among unnecessary assignments.

Take a look at the example in the editor. Run it.

This is what it prints:

`Abcd`

**output**

Try some more advanced examples and test their output:

`   print("Alpha".capitalize())  print('ALPHA'.capitalize())  print(' Alpha'.capitalize())  print('123'.capitalize())  print("αβγδ".capitalize())          `

```python
# Demonstrating the capitalize() method:
print('aBcD'.capitalize())

```
# The center() method

The one-parameter variant of the `center()` method makes a copy of the original string, trying to center it inside a field of a specified width.

The centering is actually done by **adding some spaces before and after the string**.

Don't expect this method to demonstrate any sophisticated skills. It's rather simple.

The example in the editor uses brackets to clearly show you where the centered string actually begins and terminates.

Its output looks as follows:

`[ alpha ]`

**output**

If the target field's length is too small to fit the string, the original string is returned.

You can see the `center()` method in more examples here:

`   print('[' + 'Beta'.center(2) + ']')  print('[' + 'Beta'.center(4) + ']')  print('[' + 'Beta'.center(6) + ']')   `  

Run the snippets above and check what output they produce.

  

**The two-parameter variant of `center()` makes use of the character from the second argument, instead of a space**. Analyze the example below:

`   print('[' + 'gamma'.center(20, '*') + ']')   `  

This is why the output now looks like this:

`[*******gamma********]`

**output**

Carry out more experiments.

```python
# Demonstrating the center() method:
print('[' + 'alpha'.center(10) + ']')
```
# The endswith() method

The `endswith()` method **checks if the given string ends with the specified argument and returns `True` or `False`**, depending on the check result.

Note: the substring must adhere to the string's last character - it cannot just be located somewhere near the end of the string.

Look at our example in the editor, analyze it, and run it. It outputs:

`yes`

**output**

You should now be able to predict the output of the snippet below:

`   t = "zeta"  print(t.endswith("a"))  print(t.endswith("A"))  print(t.endswith("et"))  print(t.endswith("eta"))   `  

Run the code to check your predictions.

```python
# Demonstrating the endswith() method:
if "epsilon".endswith("on"):
    print("yes")
else:
    print("no")
```
# The find() method

The `find()` method is similar to `index()`, which you already know - **it looks for a substring and returns the index of first occurrence of this substring**, but:

-   it's safer - it **doesn't generate an error for an argument containing a non-existent substring** (it returns `-1` then)
-   it **works with strings only** - don't try to apply it to any other sequence.

Look at the code in the editor. This is how you can use it.

The example prints:

`1 -1`

**output**

Note: don't use `find()` if you only want to check if a single character occurs within a string - the `in` operator will be significantly faster.

Here is another example:

`   t = 'theta'  print(t.find('eta'))  print(t.find('et'))  print(t.find('the'))  print(t.find('ha'))   `  

Can you predict the output? Run it and check your predictions.

  

If you want to perform the find, not from the string's beginning, but **from any position**, you can use a **two-parameter variant** of the `find()` method. Look at the example:

`   print('kappa'.find('a', 2))   `  

The second argument **specifies the index at which the search will be started** (it doesn't have to fit inside the string).

Among the two _a_ letters, only the second will be found. Run the snippet and check.

  

You can use the `find()` method to search for all the substring's occurrences, like here:

`   the_text = """A variation of the ordinary lorem ipsum  text has been used in typesetting since the 1960s  or earlier, when it was popularized by advertisements  for Letraset transfer sheets. It was introduced to  the Information Age in the mid-1980s by the Aldus Corporation,  which employed it in graphics and word-processing templates  for its desktop publishing program PageMaker (from Wikipedia)"""  fnd = the_text.find('the')  while fnd != -1:  print(fnd)  fnd = the_text.find('the', fnd + 1)   `  

The code prints the indices of all occurrences of the article _the_, and its output looks like this:

`15 80 198 221 238`

**output**

There is also a **three-parameter mutation of the `find()` method** - the third argument **points to the first index which won't be taken into consideration during the search** (it's actually the upper limit of the search).

Look at our example below:

`   print('kappa'.find('a', 1, 4))  print('kappa'.find('a', 2, 4))   `  

The second argument specifies the index at which the search will be started (it doesn't have to fit inside the string).

Therefore, the modified example outputs:

`1 -1`

**output**

(_a_ cannot be found within the given search boundaries in the second `print()`.

```python
# Demonstrating the find() method:
print("Eta".find("ta"))
print("Eta".find("mma"))
```
# The isalnum() method

The parameterless method named `isalnum()` **checks if the string contains only digits or alphabetical characters (letters), and returns `True` or `False`** according to the result.

Look at the example in the editor and run it.

Note: any string element that is not a digit or a letter causes the method to return `False`. An empty string does, too.

The example output is:

`True True True False False False`

**output**

Three more intriguing examples are here:

`   t = 'Six lambdas'  print(t.isalnum())  t = 'ΑβΓδ'  print(t.isalnum())  t = '20E1'  print(t.isalnum())   `  

Run them and check their output.

Hint: the cause of the first result is a space - it's neither a digit nor a letter.
```python
# Demonstrating the isalnum() method:
print('lambda30'.isalnum())
print('lambda'.isalnum())
print('30'.isalnum())
print('@'.isalnum())
print('lambda_30'.isalnum())
print(''.isalnum())
```
# The isalpha() method

The `isalpha()` method is more specialized - it's interested in **letters only**.

Look at Example 1 - its output is:

`True False`

**output**

## The isdigit() method

In turn, the `isdigit()` method looks at **digits only** - anything else produces `False` as the result.

Look at Example 2 - its output is:

`True False`

**output**

Carry out more experiments.

```python
# Example 1: Demonstrating the isapha() method:
print("Moooo".isalpha())
print('Mu40'.isalpha())

# Example 2: Demonstrating the isdigit() method:
print('2018'.isdigit())
print("Year2019".isdigit())
```
# The islower() method

The `islower()` method is a fussy variant of `isalpha()` - it accepts **lower-case letters only**.

Look at Example 1 in the editor - it outputs:

`False True`

**output**

  

## The isspace() method

The `isspace()` method **identifies whitespaces only** - it disregards any other character (the result is `False` then).

Look at Example 2 in the editor - the output is:

`True True False`

**output**

  

## The isupper() method

The `isupper()` method is the upper-case version of `islower()` - it concentrates on **upper-case letters only**.

Again, Look at the code in the editor - Example 3 produces the following output:

`False False True`

**output**

```python
# Example 1: Demonstrating the islower() method:
print("Moooo".islower())
print('moooo'.islower())

# Example 2: Demonstrating the isspace() method:
print(' \n '.isspace())
print(" ".isspace())
print("mooo mooo mooo".isspace())

# Example 3: Demonstrating the isupper() method:
print("Moooo".isupper())
print('moooo'.isupper())
print('MOOOO'.isupper())
```
# The join() method

The `join()` method is rather complicated, so let us guide you step by step thorough it:

-   as its name suggests, the method **performs a join** - it expects one argument as a list; it must be assured that all the list's elements are strings - the method will raise a TypeError exception otherwise;
-   all the list's elements will be **joined into one string** but...
-   ...the string from which the method has been invoked is **used as a separator**, put among the strings;
-   the newly created string is returned as a result.

Take a look at the example in the editor. Let's analyze it:

-   the `join()` method is invoked from within a string containing a comma (the string can be arbitrarily long, or it can be empty)
-   the `join`'s argument is a list containing three strings;
-   the method returns a new string.

Here it is:

`omicron,pi,rh`

**output**

```python
# Demonstrating the join() method:
print(",".join(["omicron", "pi", "rho"]))
```
# The lower() method

The `lower()` method **makes a copy of a source string, replaces all upper-case letters with their lower-case counterparts**, and returns the string as the result. Again, the source string remains untouched.

If the string doesn't contain any upper-case characters, the method returns the original string.

Note: The `lower()` method doesn't take any parameters.

The example in the editor outputs:

`sigma=60`

**output**

As usual, carry out your own experiments.

```python
# Demonstrating the lower() method:
print("SiGmA=60".lower())
```
# The lstrip() method

The parameterless `lstrip()` method **returns a newly created string formed from the original one by removing all leading whitespaces**.

Analyze the example code in the editor.

The brackets are not a part of the result - they only show the result's boundaries.

The example outputs:

`[tau ]`

**output**

The **one-parameter** `lstrip()` method does the same as its parameterless version, but **removes all characters enlisted in its argument** (a string), not just whitespaces:

`   print("www.cisco.com".lstrip("w."))   `  

Brackets aren't needed here, as the output looks as follows:

`cisco.com`

**output**

Can you guess the output of the snippet below? Think carefully. Run the code and check your predictions.

`   print("pythoninstitute.org".lstrip(".org"))   `  

Surprised? **Leading** characters, leading whitespaces. Again, experiment with your own examples.

```python
# Demonstrating the lstrip() method:
print("[" + " tau ".lstrip() + "]")
```
# The replace() method

The **two-parameter** `replace()` method **returns a copy of the original string in which all occurrences of the first argument have been replaced by the second argument**.

Look at the example code in the editor. Run it.

The example outputs:

`www.pythoninstitute.org Thare are it! Apple`

**output**

If the second argument is an empty string, **replacing is actually removing** the first argument's string. What kind of magic happens if the first argument is an empty string?

  

The **three-parameter** `replace()` variant uses the third argument (a number) to **limit the number of replacements**.

Look at the modified example code below:

`   print("This is it!".replace("is", "are", 1))  print("This is it!".replace("is", "are", 2))   `  

Can you guess its output? Run the code and check your guesses.

```python
# Demonstrating the replace() method:
print("www.netacad.com".replace("netacad.com", "pythoninstitute.org"))
print("This is it!".replace("is", "are"))
print("Apple juice".replace("juice", ""))
```
# The rfind() method

The one-, two-, and three-parameter methods named `rfind()` do nearly the same things as their counterparts (the ones devoid of the _r_ prefix), but **start their searches from the end of the string**, not the beginning (hence the prefix _r_, for _right_).

Take a look at the example code in the editor and try to predict its output. Run the code to check if you were right.
```python
# Demonstrating the rfind() method:
print("tau tau tau".rfind("ta"))
print("tau tau tau".rfind("ta", 9))
print("tau tau tau".rfind("ta", 3, 9))
```
# The rstrip() method

Two variants of the `rstrip()` method do nearly the same as `lstrip`s, but **affect the opposite side of the string**.

Look at the code example in the editor. Can you guess its output? Run the code to check your guesses.

As usual, we encourage you to experiment with your own examples.
```python
# Demonstrating the rstrip() method:
print("[" + " upsilon ".rstrip() + "]")
print("cisco.com".rstrip(".com"))
```
# The split() method

The `split()` method does what it says - it **splits the string and builds a list of all detected substrings**.

The method **assumes that the substrings are delimited by whitespaces** - the spaces don't take part in the operation, and aren't copied into the resulting list.

If the string is empty, the resulting list is empty too.

Look at the code in the editor. The example produces the following output:

`['phi', 'chi', 'psi']`

**output**

Note: the reverse operation can be performed by the `join()` method.

```python
# Demonstrating the split() method:
print("phi       chi\npsi".split())
```
# The startswith() method

The `startswith()` method is a mirror reflection of `endswith()` - it **checks if a given string starts with the specified substring**.

Look at the example in the editor. This is the result from it:

`False True`

**output**

## The strip() method

The `strip()` method combines the effects caused by `rstrip()` and `lstrip()` - it **makes a new string lacking all the leading and trailing whitespaces**.

Look at the second example in the editor. This is the result it returns:

`[aleph]`

**output**

Now carry out your own experiments with the two methods.
```python
# Demonstrating the startswith() method:
print("omega".startswith("meg"))
print("omega".startswith("om"))

print()

# Demonstrating the strip() method:
print("[" + "   aleph   ".strip() + "]")
```
# The swapcase() method

The `swapcase()` method **makes a new string by swapping the case of all letters within the source string**: lower-case characters become upper-case, and vice versa.

All other characters remain untouched.

Look at the first example in the editor. Can you guess the output? It won't look good, but you must see it:

`i KNOW THAT i KNOW NOTHING.`

**output**

## The title() method

The `title()` method performs a somewhat similar function - it **changes every word's first letter to upper-case, turning all other ones to lower-case**.

Look at the second example in the editor. Can you guess its output? This is the result:

`I Know That I Know Nothing. Part 1.`

**output**

## The upper() method

Last but not least, the `upper()` method **makes a copy of the source string, replaces all lower-case letters with their upper-case counterparts**, and returns the string as the result.

Look at the third example in the editor. It outputs:

`I KNOW THAT I KNOW NOTHING. PART 2.`

**output**

Hoooray! We've made it to the end of this section. Are you surprised with any of the string methods we've discussed so far? Take a couple of minutes to review them, and let's move on to the next part of the course where we'll show you what great things we can do with strings.

```python
# Demonstrating the swapcase() method:
print("I know that I know nothing.".swapcase())

print()

# Demonstrating the title() method:
print("I know that I know nothing. Part 1.".title())

print()

# Demonstrating the upper() method:
print("I know that I know nothing. Part 2.".upper())
```
# Key takeaways

  

1. Some of the methods offered by strings are:

-   `capitalize()` – changes all string letters to capitals;
-   `center()` – centers the string inside the field of a known length;
-   `count()` – counts the occurrences of a given character;
-   `join()` – joins all items of a tuple/list into one string;
-   `lower()` – converts all the string's letters into lower-case letters;
-   `lstrip()` – removes the white characters from the beginning of the string;
-   `replace()` – replaces a given substring with another;
-   `rfind()` – finds a substring starting from the end of the string;
-   `rstrip()` – removes the trailing white spaces from the end of the string;
-   `split()` – splits the string into a substring using a given delimiter;
-   `strip()` – removes the leading and trailing white spaces;
-   `swapcase()` – swaps the letters' cases (lower to upper and vice versa)
-   `title()` – makes the first letter in each word upper-case;
-   `upper()` – converts all the string's letter into upper-case letters.

  

2. String content can be determined using the following methods (all of them return Boolean values):

-   `endswith()` – does the string end with a given substring?
-   `isalnum()` – does the string consist only of letters and digits?
-   `isalpha()` – does the string consist only of letters?
-   `islower()` – does the string consists only of lower-case letters?
-   `isspace()` – does the string consists only of white spaces?
-   `isupper()` – does the string consists only of upper-case letters?
-   `startswith()` – does the string begin with a given substring?

  
  

  

**Exercise 1**

What is the expected output of the following code?

`for ch in "abc123XYX": if ch.isupper(): print(ch.lower(), end='') elif ch.islower(): print(ch.upper(), end='') else: print(ch, end='')`  
Check

`ABC123xyz`

  
  

**Exercise 2**

What is the expected output of the following code?

`s1 = 'Where are the snows of yesteryear?' s2 = s1.split() print(s2[-2])`  
Check

`of`

  
  

**Exercise 3**

What is the expected output of the following code?

`the_list = ['Where', 'are', 'the', 'snows?'] s = '*'.join(the_list) print(s)`  
Check

`Where*are*the*snows?`

  
  

**Exercise 4**

What is the expected output of the following code?

`s = 'It is either easy or impossible' s = s.replace('easy', 'hard').replace('im', '') print(s)`  
Check

`It is either hard or possible`

## Estimated time

20-25 minutes

## Level of difficulty

Medium

## Objectives

-   improving the student's skills in operating with strings;
-   using built-in Python string methods.

## Scenario

You already know how `split()` works. Now we want you to prove it.

Your task is to **write your own function, which behaves almost exactly like the original `split()` method**, i.e.:

-   it should accept exactly one argument - a string;
-   it should return a list of words created from the string, divided in the places where the string contains whitespaces;
-   if the string is empty, the function should return an empty list;
-   its name should be `mysplit()`

Use the template in the editor. Test your code carefully.

## Expected output

`['To', 'be', 'or', 'not', 'to', 'be,', 'that', 'is', 'the', 'question'] ['To', 'be', 'or', 'not', 'to', 'be,that', 'is', 'the', 'question'] [] ['abc'] []`

```python
def mysplit(strng):
    #
    # put your code here
    #


print(mysplit("To be or not to be, that is the question"))
print(mysplit("To be or not to be,that is the question"))
print(mysplit("   "))
print(mysplit(" abc "))
print(mysplit(""))
```
# Comparing strings

Python's strings **can be compared using the same set of operators** which are in use in relation to numbers.

Take a look at these operators - they can all compare strings, too:

-   `==`
-   `!=`
-   `>`
-   `>=`
-   `<`
-   `<=`

There is one "but" - the results of such comparisons may sometimes be a bit surprising. Don't forget that Python is not aware (it cannot be in any way) of subtle linguistic issues - it just **compares code point values**, character by character.

The results you get from such an operation are sometimes astonishing. Let's start with the simplest cases.

  

Two strings are equal when they consist of the same characters in the same order. By the same fashion, two strings are not equal when they don't consist of the same characters in the same order.

Both comparisons give `True` as a result:

`   'alpha' == 'alpha'  'alpha' != 'Alpha'       `  
  

The final relation between strings is determined by **comparing the first different character in both strings** (keep ASCII/UNICODE code points in mind at all times.)

When you compare two strings of different lengths and the shorter one is identical to the longer one's beginning, the **longer string is considered greater**.

Just like here:

`   'alpha' < 'alphabet'       `  

The relation is `True`.

String comparison is always case-sensitive (**upper-case letters are taken as lesser than lower-case**).

The expression is `True`:

`   'beta' > 'Beta'          `

```python
# Test examples here.
```
# Comparing strings: continued

Even **if a string contains digits only, it's still not a number**. It's interpreted as-is, like any other regular string, and its (potential) numerical aspect is not taken into consideration in any way.

Look at the examples:

`   '10' == '010'  '10' > '010'  '10' > '8'  '20' < '8'  '20' < '80'       `  

They produce the following results:

`False True False True True`

**output**

**Comparing strings against numbers is generally a bad idea.**

The only comparisons you can perform with impunity are these symbolized by the `==` and `!=` operators. The former always gives `False`, while the latter always produces `True`.

Using any of the remaining comparison operators will raise a TypeError exception.

Let's check it:

`   '10' == 10  '10' != 10  '10' == 1  '10' != 1  '10' > 10       `  

The results in this case are:

`False True False True TypeError exception`

**output**

Run all the examples, and carry out more experiments.
```python
# Test examples here.
```
# Sorting

Comparing is closely related to sorting (or rather, sorting is in fact a very sophisticated case of comparing).

This is a good opportunity to show you two possible ways to **sort lists containing strings**. Such an operation is very common in the real world - any time you see a list of names, goods, titles, or cities, you expect them to be sorted.

Let's assume that you want to sort the following list:

`   greek = ['omega', 'alpha', 'pi', 'gamma']       `  

In general, Python offers two different ways to sort lists.

The first is implemented as **a function named `sorted()`**.

The function takes one argument (a list) and **returns a new list**, filled with the sorted argument's elements. (Note: this description is a bit simplified compared to the actual implementation - we'll discuss it later.)

The original list remains untouched.

Look at the code in the editor, and run it. The snippet produces the following output:

`['omega', 'alpha', 'pi', 'gamma'] ['alpha', 'gamma', 'omega', 'pi']`

**output**

The second method affects the list itself - **no new list is created**. Ordering is performed in situ by the method named `sort()`.

The output hasn't changed:

`['omega', 'alpha', 'pi', 'gamma'] ['alpha', 'gamma', 'omega', 'pi']`

**output**

If you need an order other than non-descending, you have to convince the function/method to change its default behaviors. We'll discuss it soon.

```python
# Demonstrating the sorted() function:
first_greek = ['omega', 'alpha', 'pi', 'gamma']
first_greek_2 = sorted(first_greek)

print(first_greek)
print(first_greek_2)

print()

# Demonstrating the sort() method:
second_greek = ['omega', 'alpha', 'pi', 'gamma']
print(second_greek)

second_greek.sort()
print(second_greek)
```
# Strings vs. numbers

There are two additional issues that should be discussed here: **how to convert a number (an integer or a float) into a string, and vice versa**. It may be necessary to perform such a transformation. Moreover, it's a routine way to process input/output data.

The number-string conversion is simple, as it is always possible. It's done by a function named `str()`.

Just like here:

`   itg = 13  flt = 1.3  si = str(itg)  sf = str(flt)  print(si + ' ' + sf)   `  

The code outputs:

`13 1.3`

**output**

The reverse transformation (string-number) is possible when and only when the string represents a valid number. If the condition is not met, expect a ValueError exception.

Use the `int()` function if you want to get an integer, and `float()` if you need a floating-point value.

Just like here:

`   si = '13'  sf = '1.3'  itg = int(si)  flt = float(sf)  print(itg + flt)   `  

This is what you'll see in the console:

`14.3`

**output**

In the next section, we're going to show you some simple programs that process strings.

# Key takeaways

  

1. Strings can be compared to strings using general comparison operators, but comparing them to numbers gives no reasonable result, because **no string can be equal** to any number. For example:

-   `string == number` is always `False`;
-   `string != number` is always `True`;
-   `string >= number` always **raises an exception**.

  

2. Sorting lists of strings can be done by:

-   a function named `sorted()`, creating a new, sorted list;
-   a method named `sort()`, which sorts the list _in situ_

  

3. A number can be converted to a string using the `str()` function.

4. A string can be converted to a number (although not every string) using either the `int()` or `float()` function. The conversion fails if a string doesn't contain a valid number image (an exception is raised then).

  
  

  

**Exercise 1**

Which of the following lines describe a **true** condition?

`'smith' > 'Smith' 'Smiths' < 'Smith' 'Smith' > '1000' '11' < '8'`  
Check

1, 3 and 4

  
  

**Exercise 2**

What is the expected output of the following code?

`s1 = 'Where are the snows of yesteryear?' s2 = s1.split() s3 = sorted(s2) print(s3[1])`  
Check

`are`

  
  

**Exercise 3**

What is the expected result of the following code?

`s1 = '12.8' i = int(s1) s2 = str(i) f = float(s2) print(s1 == s2)`  
Check

The code raises a `ValueError` exception

## Estimated time

30 minutes

## Level of difficulty

Medium

## Objectives

-   improving the student's skills in operating with strings;
-   using strings to represent non-text data.

## Scenario

You've surely seen a _seven-segment display_.

It's a device (sometimes electronic, sometimes mechanical) designed to present one decimal digit using a subset of seven segments. If you still don't know what it is, refer to the following Wikipedia [article](https://en.wikipedia.org/wiki/Seven-segment_display).

Your task is to write **a program which is able to simulate the work of a seven-display device**, although you're going to use single LEDs instead of segments.

Each digit is constructed from 13 LEDs (some lit, some dark, of course) - that's how we imagine it:

`# ### ### # # ### ### ### ### ### ### # # # # # # # # # # # # # # # ### ### ### ### ### # ### ### # # # # # # # # # # # # # # # # ### ### # ### ### # ### ### ###`  

Note: the number 8 shows all the LED lights on.

Your code has to _display_ any non-negative integer number entered by the user.

Tip: using a list containing patterns of all ten digits may be very helpful.

## Test data

Sample input:

`123`  

Sample output:

`# ### ### # # # # ### ### # # # # ### ###`  

Sample input:

`9081726354`  

Sample output:

`### ### ### # ### ### ### ### ### # # # # # # # # # # # # # # # # ### # # ### # # ### ### ### ### ### # # # # # # # # # # # # # ### ### ### # # ### ### ### ### #`

# The Caesar Cipher: encrypting a message

We're going to show you four simple programs in order to present some aspects of string processing in Python. They are purposefully simple, but the lab problems will be significantly more complicated.

The first problem we want to show you is called the **Caesar cipher** - more details here: [https://en.wikipedia.org/wiki/Caesar_cipher](https://en.wikipedia.org/wiki/Caesar_cipher).

This cipher was (probably) invented and used by Gaius Julius Caesar and his troops during the Gallic Wars. The idea is rather simple - every letter of the message is replaced by its nearest consequent (_A_ becomes _B_, _B_ becomes _C_, and so on). The only exception is _Z_, which becomes _A_.

The program in the editor is a very simple (but working) implementation of the algorithm.

We've written it using the following assumptions:

-   it accepts Latin letters only (note: the Romans used neither whitespaces nor digits)
-   all letters of the message are in upper case (note: the Romans knew only capitals)

Let's trace the code:

-   line 02: ask the user to enter the open (unencrypted), one-line message;
-   line 03: prepare a string for an encrypted message (empty for now)
-   line 04: start the iteration through the message;
-   line 05: if the current character is not alphabetic...
-   line 06: ...ignore it;
-   line 07: convert the letter to upper-case (it's preferable to do it blindly, rather than check whether it's needed or not)
-   line 08: get the code of the letter and increment it by one;
-   line 09: if the resulting code has "left" the Latin alphabet (if it's greater than the _Z_ code)...
-   line 10: ...change it to the _A_ code;
-   line 11: append the received character to the end of the encrypted message;
-   line 13: print the cipher.

The code, fed with this message:

`AVE CAESAR`  

outputs:

`BWFDBFTBS`

**output**

Do your own tests.

```python
# Caesar cipher.
text = input("Enter your message: ")
cipher = ''
for char in text:
    if not char.isalpha():
        continue
    char = char.upper()
    code = ord(char) + 1
    if code > ord('Z'):
        code = ord('A')
    cipher += chr(code)

print(cipher)
```
# The Caesar Cipher: decrypting a message

The reverse transformation should now be clear to you - let's just present you with the code as-is, without any explanations.

Look at the code in the editor. Check carefully if it works. Use the cryptogram from the previous program.

```python
# Caesar cipher - decrypting a message.
cipher = input('Enter your cryptogram: ')
text = ''
for char in cipher:
    if not char.isalpha():
        continue
    char = char.upper()
    code = ord(char) - 1
    if code < ord('A'):
        code = ord('Z')
    text += chr(code)

print(text)
```
-     
    

# The Numbers Processor

The third program shows a simple method allowing you to input a line filled with numbers, and to process them easily. Note: the routine `input()` function, combined together with the `int()` or `float()` functions, is unsuitable for this purpose.

The processing will be extremely easy - we want the numbers to be summed.

Look at the code in the editor. Let's analyze it.

Using list comprehension may make the code slimmer. You can do that if you want.

Let's present our version:

-   line 03: ask the user to enter a line filled with any number of numbers (the numbers can be floats)
-   line 04: split the line receiving a list of substrings;
-   line 05: initiate the total sum to zero;
-   line 06: as the string-float conversion may raise an exception, it's best to continue with the protection of the try-except block;
-   line 07: iterate through the list...
-   line 08: ...and try to convert all its elements into float numbers; if it works, increase the sum;
-   line 09: everything is good so far, so print the sum;
-   line 10: the program ends here in the case of an error;
-   line 11: print a diagnostic message showing the user the reason for the failure.

The code has one important weakness - it displays a bogus result when the user enters an empty line. Can you fix it?

```python
# Numbers Processor.

line = input("Enter a line of numbers - separate them with spaces: ")
strings = line.split()
total = 0
try:
    for substr in strings:
        total += float(substr)
    print("The total is:", total)
except:
    print(substr, "is not a number.")
```
# The IBAN Validator

The fourth program implements (in a slightly simplified form) an algorithm used by European banks to specify account numbers. The standard named **IBAN** (International Bank Account Number) provides a simple and fairly reliable method of validating the account numbers against simple typos that can occur during rewriting of the number e.g., from paper documents, like invoices or bills, into computers.

You can find more details here: [https://en.wikipedia.org/wiki/International_Bank_Account_Number](https://en.wikipedia.org/wiki/International_Bank_Account_Number).

An IBAN-compliant account number consists of:

-   a two-letter country code taken from the ISO 3166-1 standard (e.g., _FR_ for France, _GB_ for Great Britain, _DE_ for Germany, and so on)
-   two check digits used to perform the validity checks - fast and simple, but not fully reliable, tests, showing whether a number is invalid (distorted by a typo) or seems to be good;
-   the actual account number (up to 30 alphanumeric characters - the length of that part depends on the country)

The standard says that validation requires the following steps (according to Wikipedia):

-   (step 1) Check that the total IBAN length is correct as per the country (this program won't do that, but you can modify the code to meet this requirement if you wish; note: you have to teach the code all the lengths used in Europe)
-   (step 2) Move the four initial characters to the end of the string (i.e., the country code and the check digits)
-   (step 3) Replace each letter in the string with two digits, thereby expanding the string, where _A = 10_, _B = 11_ ... _Z = 35_;
-   (step 4) Interpret the string as a decimal integer and compute the remainder of that number on division by 97; If the remainder is 1, the check digit test is passed and the IBAN might be valid.

Look at the code in the editor. Let's analyze it:

-   line 03: ask the user to enter the IBAN (the number can contain spaces, as they significantly improve number readability...
-   line 04: ...but remove them immediately)
-   line 05: the entered IBAN must consist of digits and letters only - if it doesn't...
-   line 06: ...output the message;
-   line 07: the IBAN mustn't be shorter than 15 characters (this is the shortest variant, used in Norway)
-   line 08: if it is shorter, the user is informed;
-   line 09: moreover, the IBAN cannot be longer than 31 characters (this is the longest variant, used in Malta)
-   line 10: if it is longer, make an announcement;
-   line 11: start the actual processing;
-   line 12: move the four initial characters to the number's end, and convert all letters to upper case (step 02 of the algorithm)
-   line 13: this is the variable used to complete the number, created by replacing the letters with digits (according to the algorithm's step 03)
-   line 14: iterate through the IBAN;
-   line 15: if the character is a digit...
-   line 16: just copy it;
-   line 17: otherwise...
-   line 18: ...convert it into two digits (note the way it's done here)
-   line 19: the converted form of the IBAN is ready - make an integer out of it;
-   line 20: is the remainder of the division of `iban2` by `97` equal to `1`?
-   line 21: If yes, then success;
-   line 22: Otherwise...
-   line 23: ...the number is invalid.

Let's add some test data (all these numbers are valid - you can invalidate them by changing any character).

-   British: `GB72 HBZU 7006 7212 1253 00`
-   French: `FR76 30003 03620 00020216907 50`
-   German: `DE02100100100152517108`

If you are an EU resident, you can use you own account number for tests.

```python
# IBAN Validator.

iban = input("Enter IBAN, please: ")
iban = iban.replace(' ','')

if not iban.isalnum():
    print("You have entered invalid characters.")
elif len(iban) < 15:
    print("IBAN entered is too short.")
elif len(iban) > 31:
    print("IBAN entered is too long.")
else:
    iban = (iban[4:] + iban[0:4]).upper()
    iban2 = ''
    for ch in iban:
        if ch.isdigit():
            iban2 += ch
        else:
            iban2 += str(10 + ord(ch) - ord('A'))
    iban = int(iban2)
    if iban % 97 == 1:
        print("IBAN entered is valid.")
    else:
        print("IBAN entered is invalid.")
```
# Key takeaways

  

1. Strings are key tools in modern data processing, as most useful data are actually strings. For example, using a web search engine (which seems quite trivial these days) utilizes extremely complex and complicated string processing, involving unimaginable amounts of data.

2. Comparing strings in a strict way (as Python does) can be very unsatisfactory when it comes to advanced searches (e.g. during extensive database queries). Responding to this demand, a number of _fuzzy_ string comparison algorithms has been created and implemented. These algorithms are able to find strings which aren't equal in the Python sense, but are **similar**.

One such concept is the **Hamming distance**, which is used to determine the similarity of two strings. If this problem interests you, you can find out more about it here: [https://en.wikipedia.org/wiki/Hamming_distance](https://en.wikipedia.org/wiki/Hamming_distance). Another solution of the same kind, but based on a different assumption, is the **Levenshtein distance** described here: [https://en.wikipedia.org/wiki/Levenshtein_distance](https://en.wikipedia.org/wiki/Levenshtein_distance).

  
  

  

3. Another way of comparing strings is finding their _acoustic_ similarity, which means a process leading to determine if two strings sound similar (like "raise" and "race"). Such a similarity has to be established for every language (or even dialect) separately.

An algorithm used to perform such a comparison for the English language is called **Soundex** and was invented – you won't believe – in 1918. You can find out more about it here: [https://en.wikipedia.org/wiki/Soundex](https://en.wikipedia.org/wiki/Soundex).

  

1. Due to limited native float and integer data precision, it's sometimes reasonable to store and process huge numeric values as strings. This is the technique Python uses when you force it to operate on an integer number consisting of a very large number of digits.
## Estimated time

30-90 minutes

## Level of difficulty

Hard

## Pre-requisites

Module 1.11.1.1, Module 1.11.1.2

## Objectives

-   improving the student's skills in operating with strings;
-   converting characters into ASCII code, and vice versa.

## Scenario

You are already familiar with the Caesar cipher, and this is why we want you to improve the code we showed you recently.

The original Caesar cipher shifts each character by one: _a_ becomes _b_, _z_ becomes _a_, and so on. Let's make it a bit harder, and allow the shifted value to come from the range 1..25 inclusive.

Moreover, let the code preserve the letters' case (lower-case letters will remain lower-case) and all non-alphabetical characters should remain untouched.

Your task is to write a program which:

-   asks the user for one line of text to encrypt;
-   asks the user for a shift value (an integer number from the range 1..25 - note: you should force the user to enter a valid shift value (don't give up and don't let bad data fool you!)
-   prints out the encoded text.

Test your code using the data we've provided.

## Test data

Sample input:

`abcxyzABCxyz 123 2`  

Sample output:

`cdezabCDEzab 123`  

Sample input:

`The die is cast 25`  

Sample output:

`Sgd chd hr bzrs`
## Estimated time

15-30 minutes

## Level of difficulty

Easy

## Objectives

-   improving the student's skills in operating with strings;
-   encouraging the student to look for non-obvious solutions.

## Scenario

Do you know what a palindrome is?

It's a word which look the same when read forward and backward. For example, "kayak" is a palindrome, while "loyal" is not.

Your task is to write a program which:

-   asks the user for some text;
-   checks whether the entered text is a palindrome, and prints result.

Note:

-   assume that an empty string isn't a palindrome;
-   treat upper- and lower-case letters as equal;
-   spaces are not taken into account during the check - treat them as non-existent;
-   there are more than a few correct solutions - try to find more than one.

Test your code using the data we've provided.

## Test data

Sample input:

`Ten animals I slam in a net`  

Sample output:

`It's a palindrome`  
  

Sample input:

`Eleven animals I slam in a net`  

Sample output:

`It's not a palindrome`

## Estimated time

30-60 minutes

## Level of difficulty

Easy

## Objectives

-   improving the student's skills in operating with strings;
-   converting strings into lists, and vice versa.

## Scenario

An anagram is a new word formed by rearranging the letters of a word, using all the original letters exactly once. For example, the phrases "rail safety" and "fairy tales" are anagrams, while "I am" and "You are" are not.

Your task is to write a program which:

-   asks the user for two separate texts;
-   checks whether, the entered texts are anagrams and prints the result.

Note:

-   assume that two empty strings are not anagrams;
-   treat upper- and lower-case letters as equal;
-   spaces are not taken into account during the check - treat them as non-existent

Test your code using the data we've provided.

## Test data

Sample input:

`Listen Silent`  

Sample output:

`Anagrams`  
  

Sample input:

`modern norman`  

Sample output:

`Not anagrams`
## Estimated time

15-30 minutes

## Level of difficulty

Easy

## Objectives

-   improving the student's skills in operating with strings;
-   converting integers into strings, and vice versa.

## Scenario

Some say that the _Digit of Life_ is a digit evaluated using somebody's birthday. It's simple - you just need to sum all the digits of the date. If the result contains more than one digit, you have to repeat the addition until you get exactly one digit. For example:

-   1 January 2017 = 2017 01 01
-   2 + 0 + 1 + 7 + 0 + 1 + 0 + 1 = 12
-   1 + 2 = 3

_3_ is the digit we searched for and found.

Your task is to write a program which:

-   asks the user her/his birthday (in the format YYYYMMDD, or YYYYDDMM, or MMDDYYYY - actually, the order of the digits doesn't matter)
-   outputs the _Digit of Life_ for the date.

Test your code using the data we've provided.

## Test data

Sample input:

`19991229`  

Sample output:

`6`  
  

Sample input:

`20000101`  

Sample output:

`4`

## Estimated time

30-45 minutes

## Level of difficulty

Medium

## Objectives

-   improving the student's skills in operating with strings;
-   using the `find()` method for searching strings.

## Scenario

Let's play a game. We will give you two strings: one being a word (e.g., "dog") and the second being a combination of any characters.

Your task is to write a program which answers the following question: **are the characters comprising the first string hidden inside the second string?**

For example:

-   if the second string is given as "vcxzxduybfdsobywuefgas", the answer is `yes`;
-   if the second string is "vcxzxdcybfdstbywuefsas", the answer is `no` (as there are neither the letters "d", "o", or "g", in this order)

Hints:

-   you should use the two-argument variants of the `pos()` functions inside your code;
-   don't worry about case sensitivity.

Test your code using the data we've provided.

## Test data

Sample input:

`donor Nabucodonosor`

Sample output:

`Yes`  
  

Sample input:

`donut Nabucodonosor`

Sample output:

`No`
## Estimated time

60-90 minutes

## Level of difficulty

Hard

## Objectives

-   improving the student's skills in operating with strings and lists;
-   converting strings into lists.

## Scenario

As you probably know, _Sudoku_ is a number-placing puzzle played on a 9x9 board. The player has to fill the board in a very specific way:

-   each row of the board must contain all digits from 0 to 9 (the order doesn't matter)
-   each column of the board must contain all digits from 0 to 9 (again, the order doesn't matter)
-   each of the nine 3x3 "tiles" (we will name them "sub-squares") of the table must contain all digits from 0 to 9.

If you need more details, you can find them [here](https://en.wikipedia.org/wiki/Sudoku).

Your task is to write a program which:

-   reads 9 rows of the Sudoku, each containing 9 digits (check carefully if the data entered are valid)
-   outputs `Yes` if the Sudoku is valid, and `No` otherwise.

Test your code using the data we've provided.

## Test data

Sample input:

`295743861 431865927 876192543 387459216 612387495 549216738 763524189 928671354 154938672`

Sample output:

`Yes`  
  

Sample input:

`195743862 431865927 876192543 387459216 612387495 549216738 763524189 928671354 254938671`

Sample output:

`No`

# Errors, failures, and other plagues

**Anything that can go wrong, will go wrong**.

This is Murphy's law, and it works everywhere and always. Your code's execution can go wrong, too. If it can, it will.

Look the code in the editor. There are at least two possible ways it can "go wrong". Can you see them?

-   As a user is able to enter a completely arbitrary string of characters, **there is no guarantee that the string can be converted into a float value** - this is the first vulnerability of the code;
-   the second is that the **`sqrt()` function fails if it gets a negative argument**.

You may get one of the following error messages.

Something like this:

`Enter x: Abracadabra Traceback (most recent call last): File "sqrt.py", line 3, in <module> x = float(input("Enter x: ")) ValueError: could not convert string to float: 'Abracadabra'`

**output**

Or something like this:

`Enter x: -1 Traceback (most recent call last): File "sqrt.py", line 4, in <module> y = math.sqrt(x) ValueError: math domain error`

**output**

Can you protect yourself from such surprises? Of course you can. Moreover, you have to do it in order to be considered a good programmer.

```python
import math

x = float(input("Enter x: "))
y = math.sqrt(x)

print("The square root of", x, "equals to", y)
```
# Exceptions

Each time your code tries to do something wrong/foolish/irresponsible/crazy/unenforceable, Python does two things:

-   it **stops your program**;
-   it creates a special kind of data, called an **exception**.

Both of these activities are called **raising an exception**. We can say that Python always raises an exception (or that an **exception has been raised**) when it has no idea what to do with your code.

What happens next?

-   the raised exception expects somebody or something to notice it and take care of it;
-   if nothing happens to take care of the raised exception, the program will be **forcibly terminated**, and you will see an **error message** sent to the console by Python;
-   otherwise, if the exception is taken care of and **handled** properly, the suspended program can be resumed and its execution can continue.

Python provides effective tools that allow you to **observe exceptions, identify them and handle them** efficiently. This is possible due to the fact that all potential exceptions have their unambiguous names, so you can categorize them and react appropriately.
![[Pasted image 20221224105653.png]]
You know some exception names already. Take a look at the following diagnostic message:

`ValueError: math domain error`

**output**

The word highlighted above is just the **exception name**. Let's get familiar with some other exceptions.
# Exceptions: continued

Look at the code in the editor. Run the (obviously incorrect) program.

You will see the following message in reply:

`Traceback (most recent call last): File "div.py", line 2, in value /= 0 ZeroDivisionError: division by zero`

**output**

This exception error is called **ZeroDivisionError**.
```python
value = 1
value /= 0
```
# Exceptions: continued

Look at the code in the editor. What will happen when you run it? Check.

You will see the following message in reply:

`Traceback (most recent call last): File "lst.py", line 2, in x = list[0] IndexError: list index out of range`

**output**

This is the **IndexError**.

```python
my_list = []
x = my_list[0]
```
# Exceptions: continued

How do you **handle** exceptions? The word `try` is key to the solution.

What's more, it's a keyword, too.

The recipe for success is as follows:

-   first, you have to **_try_ to do something**;
-   next, you have to **check whether everything went well**.

But wouldn't it be better to check all circumstances first and then do something only if it's safe?

Just like the example in the editor.

Admittedly, this way may seem to be the most natural and understandable, but in reality, this method doesn't make programming any easier. All these checks can make **your code bloated and illegible**.

Python prefers a completely different approach.
```python
first_number = int(input("Enter the first number: "))
second_number = int(input("Enter the second number: "))

if second_number != 0:
    print(first_number / second_number)
else:
    print("This operation cannot be done.")

print("THE END.")
```
# Exceptions: continued

Look at the code in the editor. This is the favorite Python approach.

Note:

-   the `try` keyword **begins a block of the code** which may or may not be performing correctly;
-   next, Python tries to perform the risky action; if it fails, an exception is raised and Python starts to look for a solution;
-   the `except` keyword starts a piece of code which will be **executed if anything inside the `try` block goes wrong** - if an exception is raised inside a previous `try` block, **it will fail here**, so the code located after the except keyword should provide an **adequate reaction** to the raised exception;
-   returning to the previous nesting level ends the **try-except** section.

Run the code and test its behavior.

  

Let's summarize this:

`   try:  :  :  except:  :  :       `  

-   in the first step, Python tries to perform all instructions placed between the `try:` and `except:` statements;
-   if nothing is wrong with the execution and all instructions are performed successfully, the execution jumps to the point after the last line of the `except:` block, and the block's execution is considered complete;
-   if anything goes wrong inside the `try:` and `except:` block, the execution immediately jumps out of the block and into the first instruction located after the `except:` keyword; this means that some of the instructions from the block may be silently omitted.
```python
first_number = int(input("Enter the first number: "))
second_number = int(input("Enter the second number: "))

try:
    print(first_number / second_number)
except:
    print("This operation cannot be done.")

print("THE END.")
```
# Exceptions: continued

Look at the code in the editor. It will help you understand this mechanism.

This is the output it produces:

`1 Oh dear, something went wrong... 3`

**output**

Note: the `print("2")` instruction was lost in the process.
```python
try:
    print("1")
    x = 1 / 0
    print("2")
except:
    print("Oh dear, something went wrong...")

print("3")
```
# Exceptions: continued

This approach has one important disadvantage - if there is a possibility that more than one exception may skip into an `except:` branch, you may have **trouble figuring out what actually happened**.

Just like in our code in the editor. Run it and see what happens.

The message: `Oh dear, something went wrong...` appearing in the console says nothing about the reason, while there are two possible causes of the exception:

-   non-integer data entered by the user;
-   an integer value equal to `0` assigned to the `x` variable.

  

Technically, there are two ways to solve the issue:

-   build two consecutive try-except blocks, one for each possible exception reason (easy, but will cause unfavorable code growth)
-   use a more advanced variant of the instruction.

It looks like this:

`   try:  :  except exc1:  :  except exc2:  :  except:  :       `  

This is how it works:

-   if the `try` branch raises the `exc1` exception, it will be handled by the `except exc1:` block;
-   similarly, if the `try` branch raises the `exc2` exception, it will be handled by the `except exc2:` block;
-   if the `try` branch raises any other exception, it will be handled by the unnamed `except` block.

Let's move on to the next part of the course and see it in action.

```python
try:
    x = int(input("Enter a number: "))
    y = 1 / x
except:
    print("Oh dear, something went wrong...")

print("THE END.")
```
# Exceptions: continued

Look at the code in the editor. Our solution is there.

The code, when run, produces one of the following four variants of output:

-   if you enter a valid, non-zero integer value (e.g., `5`) it says:  
      
    `0.2 THE END.`
    
    **output**
    
-   if you enter `0`, it says:  
      
    `You cannot divide by zero, sorry. THE END.`
    
    **output**
    
-   if you enter any non-integer string, you see:  
      
    `You must enter an integer value. THE END.`
    
    **output**
    
-   (locally on your machine) if you press Ctrl-C while the program is waiting for the user's input (which causes an exception named KeyboardInterrupt), the program says:  
      
    `Oh dear, something went wrong... THE END.`
    
    **output**
```python
try:
    x = int(input("Enter a number: "))
    y = 1 / x
    print(y)
except ZeroDivisionError:
    print("You cannot divide by zero, sorry.")
except ValueError:
    print("You must enter an integer value.")
except:
    print("Oh dear, something went wrong...")

print("THE END.")
```
# Exceptions: continued

Don't forget that:

-   the `except` branches are searched in the same order in which they appear in the code;
-   you must not use more than one except branch with a certain exception name;
-   the number of different `except` branches is arbitrary - the only condition is that if you use `try`, you must put at least one `except` (named or not) after it;
-   the `except` keyword must not be used without a preceding `try`;
-   if any of the `except` branches is executed, no other branches will be visited;
-   if none of the specified `except` branches matches the raised exception, the exception remains unhandled (we'll discuss it soon)
-   if an unnamed `except` branch exists (one without an exception name), it has to be specified as the last.

`   try:  :  except exc1:  :  except exc2:  :  except:  :       `  

Let's continue the experiments now.

  

Look at the code in the editor. We've modified the previous program - we've removed the `ZeroDivisionError` branch.

What happens now if the user enters `0` as an input?

As there are **no dedicated branches** for division by zero, the raised exception falls into the **general (unnamed) branch**; this means that in this case, the program will say:

`Oh dear, something went wrong... THE END.`

**output**

Try it yourself. Run the program.

```python
try:
    x = int(input("Enter a number: "))
    y = 1 / x
    print(y)
except ValueError:
    print("You must enter an integer value.")
except:
    print("Oh dear, something went wrong...")

print("THE END.")
```
# Exceptions: continued

Let's spoil the code once again.

Look at the program in the editor. This time, we've removed the unnamed branch.

The user enters `0` once again and:

-   the exception raised won't be handled by `ValueError` - it has nothing to do with it;
-   as there's no other branch, you should to see this message:  
      
    `Traceback (most recent call last): File "exc.py", line 3, in y = 1 / x ZeroDivisionError: division by zero`
    
    **output**
    

  

You've learned a lot about exception handling in Python. In the next section, we will focus on Python built-in exceptions and their hierarchies.

```python
try:
    x = int(input("Enter a number: "))
    y = 1 / x
    print(y)
except ValueError:
    print("You must enter an integer value.")

print("THE END.")
```
# Key takeaways

  

1. An exception is an event in a program execution's life caused by an abnormal situation. The exception should he handled to avoid program termination. The part of your code that is suspected of being the source of the exception should be put inside the `try` branch.

When the exception happens, the execution of the code is not terminated, but instead jumps into the `except` branch. This is the place where the handling of the exception should take place. The general scheme for such a construction looks as follows:

`   :  # The code that always runs smoothly.  :  try:  :  # Risky code.  :  except:  :  # Crisis management takes place here.  :  :  # Back to normal.  :       `  

2. If you need to handle more than one exception coming from the same `try` branch ,you can add more than one `except` branch, but you have to label them with different exception names, like this:

`   :  # The code that always runs smoothly.  :  try:  :  # Risky code.  :  except Except_1:  # Crisis management takes place here.  except Except_2:  # We save the world here.  :  # Back to normal.  :       `  

At most, one of the `except` branches is executed – none of the branches is performed when the raised exception doesn't match to the specified exceptions.

  

3. You cannot add more than one anonymous (unnamed) `except` branch after the named ones.

`   :  # The code that always runs smoothly.  :  try:  :  # Risky code.  :  except Except_1:  # Crisis management takes place here.  except Except_2:  # We save the world here.  except:  # All other issues fall here.  :  # Back to normal.  :       `  

  

**Exercise 1**

What is the expected output of the following code?

`try: print("Let's try to do this") print("#"[2]) print("We succeeded!") except: print("We failed") print("We're done")`  
Check

`Let's try to do this We failed We're done`

  
  

**Exercise 2**

What is the expected output of the following code?

`try: print("alpha"[1/0]) except ZeroDivisionError: print("zero") except IndexingError: print("index") except: print("some")`  
Check

`zero`

# Exceptions

Python 3 defines **63 built-in exceptions**, and all of them form a **tree-shaped hierarchy**, although the tree is a bit weird as its root is located on top.

Some of the built-in exceptions are more general (they include other exceptions) while others are completely concrete (they represent themselves only). We can say that **the closer to the root an exception is located, the more general (abstract) it is**. In turn, the exceptions located at the branches' ends (we can call them **leaves**) are concrete.

Take a look at the figure:

![[Pasted image 20221224110527.png]]
It shows a small section of the complete exception tree. Let's begin examining the tree from the ZeroDivisionError leaf.

  
  

  

Note:

-   ZeroDivisionError is a special case of more a general exception class named ArithmeticError;
-   ArithmeticError is a special case of a more general exception class named just Exception;
-   Exception is a special case of a more general class named BaseException;

We can describe it in the following way (note the direction of the arrows - they always point to the more general entity):

BaseException  
↑  
Exception  
↑  
ArithmeticError  
↑  
ZeroDivisionError

  

We're going to show you how this generalization works. Let's start with some really simple code.

# Exceptions: continued

Look at the code in the editor. It is a simple example to start with. Run it.

The output we expect to see looks like this:

`Oooppsss... THE END.`

**output**

Now look at the code below:

`   try:  y = 1 / 0  except ArithmeticError:  print("Oooppsss...")  print("THE END.")   `  

Something has changed in it - we've replaced `ZeroDivisionError` with `ArithmeticError`.

You already know that `ArithmeticError` is a general class including (among others) the `ZeroDivisionError` exception.

Thus, the code's output remains unchanged. Test it.

This also means that replacing the exception's name with either `Exception` or `BaseException` won't change the program's behavior.

  

Let's summarize:

-   each exception raised **falls into the first matching branch**;
-   the matching branch doesn't have to specify the same exception exactly - it's enough that the exception is **more general** (more abstract) than the raised one.
```python
try:
    y = 1 / 0
except ZeroDivisionError:
    print("Oooppsss...")

print("THE END.")

```
# Exceptions: continued

Look at the code in the editor. What will happen here?

The first matching branch is the one containing `ZeroDivisionError`. It means that the console will show:

`Zero division! THE END.`

**output**

Will it change anything if we swap the two `except` branches around? Just like here below:

`   try:  y = 1 / 0  except ArithmeticError:  print("Arithmetic problem!")  except ZeroDivisionError:  print("Zero Division!")  print("THE END.")   `  

The change is radical - the code's output is now:

`Arithmetic problem! THE END.`

**output**

Why, if the exception raised is the same as previously?

The exception is the same, but the more general exception is now listed first - it will catch all zero divisions too. It also means that there's no chance that any exception hits the ZeroDivisionError branch. This branch is now completely unreachable.

Remember:

-   the order of the branches matters!
-   don't put more general exceptions before more concrete ones;
-   this will make the latter one unreachable and useless;
-   moreover, it will make your code messy and inconsistent;
-   Python won't generate any error messages regarding this issue.
```python
try:
    y = 1 / 0
except ZeroDivisionError:
    print("Zero Division!")
except ArithmeticError:
    print("Arithmetic problem!")

print("THE END.")
```
# Exceptions: continued

If you want to **handle two or more exceptions** in the same way, you can use the following syntax:

`   try:  :  except (exc1, exc2):  :       `  

You simply have to put all the engaged exception names into a comma-separated list and not to forget the parentheses.

  

If an **exception is raised inside a function**, it can be handled:

-   inside the function;
-   outside the function;

Let's start with the first variant - look at the code in the editor.

The ZeroDivisionError exception (being a concrete case of the ArithmeticError exception class) is raised inside the `bad_fun()` function, and it doesn't leave the function - the function itself takes care of it.

The program outputs:

`Arithmetic problem! THE END.`

**output**

  

It's also possible to let the exception propagate **outside the function**. Let's test it now.

Look at the code below:

`   def bad_fun(n):  return 1 / n  try:  bad_fun(0)  except ArithmeticError:  print("What happened? An exception was raised!")  print("THE END.")   `  

The problem has to be solved by the invoker (or by the invoker's invoker, and so on).

The program outputs:

`What happened? An exception was raised! THE END.`

**output**

  

Note: the **exception raised can cross function and module boundaries**, and travel through the invocation chain looking for a matching `except` clause able to handle it.

If there is no such clause, the exception remains unhandled, and Python solves the problem in its standard way - **by terminating your code and emitting a diagnostic message**.

Now we're going to suspend this discussion, as we want to introduce you to a brand new Python instruction.

```python
def bad_fun(n):
    try:
        return 1 / n
    except ArithmeticError:
        print("Arithmetic Problem!")
    return None

bad_fun(0)

print("THE END.")
```
# Exceptions: continued

The `raise` instruction raises the specified exception named `exc` as if it was raised in a normal (natural) way:

`   raise exc       `  

Note: `raise` is a keyword.

The instruction enables you to:

-   **simulate raising actual exceptions** (e.g., to test your handling strategy)
-   partially **handle an exception** and make another part of the code responsible for completing the handling (separation of concerns).

Look at the code in the editor. This is how you can use it in practice.

The program's output remains unchanged.

In this way, you can **test your exception handling routine** without forcing the code to do stupid things.

```python
def bad_fun(n):
    raise ZeroDivisionError


try:
    bad_fun(0)
except ArithmeticError:
    print("What happened? An error?")

print("THE END.")
```
# Exceptions: continued

The `raise` instruction may also be utilized in the following way (note the absence of the exception's name):

`   raise       `  

There is one serious restriction: this kind of `raise` instruction may be used **inside the `except` branch** only; using it in any other context causes an error.

The instruction will immediately re-raise the same exception as currently handled.

  

Thanks to this, you can distribute the exception handling among different parts of the code.

Look at the code in the editor. Run it - we'll see it in action.

The ZeroDivisionError is raised twice:

-   first, inside the `try` part of the code (this is caused by actual zero division)
-   second, inside the `except` part by the `raise` instruction.

In effect, the code outputs:

`I did it again! I see! THE END.`

**output**

```python
def bad_fun(n):
    try:
        return n / 0
    except:
        print("I did it again!")
        raise


try:
    bad_fun(0)
except ArithmeticError:
    print("I see!")

print("THE END.")
```
# Exceptions: continued

Now is a good moment to show you another Python instruction, named `assert`. This is a keyword.

`   assert expression       `  

How does it work?

-   It evaluates the expression;
-   if the expression evaluates to `True`, or a non-zero numerical value, or a non-empty string, or any other value different than `None`, it won't do anything else;
-   otherwise, it automatically and immediately raises an exception named AssertionError (in this case, we say that the assertion has failed)

How it can be used?

-   you may want to put it into your code where you want to be **absolutely safe from evidently wrong data**, and where you aren't absolutely sure that the data has been carefully examined before (e.g., inside a function used by someone else)
-   raising an AssertionError exception secures your code from producing invalid results, and clearly shows the nature of the failure;
-   **assertions don't supersede exceptions or validate the data** - they are their supplements.

If exceptions and data validation are like careful driving, assertion can play the role of an airbag.

  

Let's see the `assert` instruction in action. Look at the code in the editor. Run it.

The program runs flawlessly if you enter a valid numerical value greater than or equal to zero; otherwise, it stops and emits the following message:

`Traceback (most recent call last): File ".main.py", line 4, in assert x >= 0.0 AssertionError`

**output**

```python
import math

x = float(input("Enter a number: "))
assert x >= 0.0

x = math.sqrt(x)

print(x)
```
# Key takeaways

  

1. You cannot add more than one anonymous (unnamed) `except` branch after the named ones.

`   :  # The code that always runs smoothly.  :  try:  :  # Risky code.  :  except Except_1:  # Crisis management takes place here.  except Except_2:  # We save the world here.  except:  # All other issues fall here.  :  # Back to normal.  :       `  

2. All the predefined Python exceptions form a hierarchy, i.e. some of them are more general (the one named `BaseException` is the most general one) while others are more or less concrete (e.g. `IndexError` is more concrete than `LookupError`).

You shouldn't put more concrete exceptions before the more general ones inside the same `except` branche sequence. For example, you can do this:

`   try:  # Risky code.  except IndexError:  # Taking care of mistreated lists  except LookupError:  # Dealing with other erroneous lookups       `  

but don't do that (unless you're absolutely sure that you want some part of your code to be useless)

`   try:  # Risky code.  except LookupError:  # Dealing with erroneous lookups  except IndexError:  # You'll never get here       `  

3. The Python statement `raise ExceptionName` can raise an exception on demand. The same statement, but lacking _ExceptionName_, can be used inside the `try` branch **only**, and raises the same exception which is currently being handled.

  

4. The Python statement `assert expression` evaluates the _expression_ and raises the `AssertError` exception when the _expression_ is equal to zero, an empty string, or `None`. You can use it to protect some critical parts of your code from devastating data.

  

  

**Exercise 1**

What is the expected output of the following code?

`try: print(1/0) except ZeroDivisionError: print("zero") except ArithmeticError: print("arith") except: print("some")`  
Check

`zero`

  
  

**Exercise 2**

What is the expected output of the following code?

`try: print(1/0) except ArithmeticError: print("arith") except ZeroDivisionError: print("zero") except: print("some")`  
Check

`arith`

  
  

**Exercise 3**

What is the expected output of the following code?

`def foo(x): assert x return 1/x try: print(foo(0)) except ZeroDivisionError: print("zero") except: print("some")`  
Check

`some`

# Built-in exceptions

We're going to show you a short list of the most useful exceptions. While it may sound strange to call "useful" a thing or a phenomenon which is a visible sign of failure or setback, as you know, to err is human and if anything can go wrong, it will go wrong.

Exceptions are as routine and normal as any other aspect of a programmer's life.

For each exception, we'll show you:

-   its name;
-   its location in the exception tree;
-   a short description;
-   a concise snippet of code showing the circumstances in which the exception may be raised.

There are lots of other exceptions to explore - we simply don't have the space to go through them all here.

## ArithmeticError

**Location:** BaseException ← Exception ← ArithmeticError

**Description:** an abstract exception including all exceptions caused by arithmetic operations like zero division or an argument's invalid domain

## AssertionError

**Location:** BaseException ← Exception ← AssertionError

**Description:** a concrete exception raised by the assert instruction when its argument evaluates to `False`, `None`, `0`, or an empty string

**Code:**

`   from math import tan, radians  angle = int(input('Enter integral angle in degrees: '))  # We must be sure that angle != 90 + k * 180  assert angle % 180 != 90  print(tan(radians(angle)))   `  
  

## BaseException

**Location:** BaseException

**Description:** the most general (abstract) of all Python exceptions - all other exceptions are included in this one; it can be said that the following two except branches are equivalent: `except:` and `except BaseException:`.

## IndexError

**Location:** BaseException ← Exception ← LookupError ← IndexError

**Description:** a concrete exception raised when you try to access a non-existent sequence's element (e.g., a list's element)

**Code:**

`   # The code shows an extravagant way  # of leaving the loop.  the_list = [1, 2, 3, 4, 5]  ix = 0  do_it = True  while do_it:  try:  print(the_list[ix])  ix += 1  except IndexError:  do_it = False  print('Done')   `

## KeyboardInterrupt

**Location:** BaseException ← KeyboardInterrupt

**Description:** a concrete exception raised when the user uses a keyboard shortcut designed to terminate a program's execution (_Ctrl-C_ in most OSs); if handling this exception doesn't lead to program termination, the program continues its execution.

Note: this exception is not derived from the Exception class. Run the program in IDLE.

**Code:**

`   # This code cannot be terminated  # by pressing Ctrl-C.  from time import sleep  seconds = 0  while True:  try:  print(seconds)  seconds += 1  sleep(1)  except KeyboardInterrupt:  print("Don't do that!")   `  

## LookupError

**Location:** BaseException ← Exception ← LookupError

**Description:** an abstract exception including all exceptions caused by errors resulting from invalid references to different collections (lists, dictionaries, tuples, etc.)

  
  

## MemoryError

**Location:** BaseException ← Exception ← MemoryError

**Description:** a concrete exception raised when an operation cannot be completed due to a lack of free memory.

**Code:**

`   # This code causes the MemoryError exception.  # Warning: executing this code may affect your OS.  # Don't run it in production environments!  string = 'x'  try:  while True:  string = string + string  print(len(string))  except MemoryError:  print('This is not funny!')   `  

## OverflowError

**Location:** BaseException ← Exception ← ArithmeticError ← OverflowError

**Description:** a concrete exception raised when an operation produces a number too big to be successfully stored

**Code:**

`   # The code prints subsequent  # values of exp(k), k = 1, 2, 4, 8, 16, ...  from math import exp  ex = 1  try:  while True:  print(exp(ex))  ex *= 2  except OverflowError:  print('The number is too big.')   `

## ImportError

**Location:** BaseException ← Exception ← StandardError ← ImportError

**Description:** a concrete exception raised when an import operation fails

**Code:**

`   # One of these imports will fail - which one?  try:  import math  import time  import abracadabra  except:  print('One of your imports has failed.')   `  
  

## KeyError

**Location:** BaseException ← Exception ← LookupError ← KeyError

**Description:** a concrete exception raised when you try to access a collection's non-existent element (e.g., a dictionary's element)

**Code:**

`   # How to abuse the dictionary  # and how to deal with it?  dictionary = { 'a': 'b', 'b': 'c', 'c': 'd' }  ch = 'a'  try:  while True:  ch = dictionary[ch]  print(ch)  except KeyError:  print('No such key:', ch)   `  

We are done with exceptions for now, but they'll return when we discuss object-oriented programming in Python. You can use them to protect your code from bad accidents, but you also have to learn how to dive into them, exploring the information they carry.

Exceptions are in fact objects - however, we can tell you nothing about this aspect until we present you with classes, objects, and the like.

For the time being, if you'd like to learn more about exceptions on your own, you look into Standard Python Library at [https://docs.python.org/3.6/library/exceptions.html](https://docs.python.org/3.6/library/exceptions.html).

## Estimated time

15-25 minutes

## Level of difficulty

Medium

## Objectives

-   improving the student's skills in defining functions;
-   using exceptions in order to provide a safe input environment.

## Scenario

Your task is to write a **function able to input integer values and to check if they are within a specified range**.

The function should:

-   accept three arguments: a prompt, a low acceptable limit, and a high acceptable limit;
-   if the user enters a string that is not an integer value, the function should emit the message `Error: wrong input`, and ask the user to input the value again;
-   if the user enters a number which falls outside the specified range, the function should emit the message `Error: the value is not within permitted range (min..max)` and ask the user to input the value again;
-   if the input value is valid, return it as a result.

## Test data

Test your code carefully.

This is how the function should react to the user's input:

`Enter a number from -10 to 10: 100 Error: the value is not within permitted range (-10..10) Enter a number from -10 to 10: asd Error: wrong input Enter number from -10 to 10: 1 The number is: 1`

```python
def read_int(prompt, min, max):
    #
    # Write your code here.
    #


v = read_int("Enter a number from -10 to 10: ", -10, 10)

print("The number is:", v)
```
# Key takeaways

  

1. Some abstract built-in Python exceptions are:

-   `ArithmeticError`,
-   `BaseException`,
-   `LookupError`.

  

2. Some concrete built-in Python exceptions are:

-   `AssertionError`,
-   `ImportError`,
-   `IndexError`,
-   `KeyboardInterrupt`,
-   `KeyError`,
-   `MemoryError`,
-   `OverflowError`.

  

  

**Exercise 1**

Which of the exceptions will you use to protect your code from being interrupted through the use of the keyboard?

Check

`KeyboardInterrupt`

  
  

**Exercise 2**

What is the name of the most general of all Python exceptions?

Check

`BaseException`

  
  

**Exercise 3**

Which of the exceptions will be raised through the following unsuccessful evaluation?

`huge_value = 1E250 ** 2`  
Check

`OverflowError`

