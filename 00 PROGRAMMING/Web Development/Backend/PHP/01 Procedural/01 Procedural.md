---
topic: php
_filters: []
_contexts: []
_links: []
_sort:
  field: rank
  asc: false
  group: false
---
Tags/Topics: #php
∗:[[01 Javascript|JavaScript]] 

---
# Syntax

--- 

> [!info] Closing tag
> If the file is __pure `PHP`__ then the ___Closing tags___ is not needed.
> 
> Else if it's included in the html:
> 
> ```php
> < ?php
> 
> ? >
> ```

>[!danger] Semi-colons are IMPORTANT!
> ```php
> echo 'Hello World';
> echo 'Hi, Universe';
> echo "Last line doesn't need a semi-colon"
> ```


>[!tip] Printing
>```php
>echo 'Hello World';
>
>echo('Hello World');
>print('Hello World');
>```
>
>> [!abstract] Parentheses `( )`
>> We can __concatenate__ strings if we don't use Parentheses.
>> ```php
>> echo 'Hello', ' ', 'World'; // Hello World
>> 
>> echo('Hello', ' ', 'World'); // Parse Error!
>> ```
>
>> [!caution] `print` vs `echo`
>> __`echo`__ has no return value.
>> while, ___`print`___ has return value of __1__.
>> ```php
>> echo print 'Hello World';  // Hello World1
>> ```
>
>
>>[!tip] Quotes inside a string
>>2 Ways to use Quotes inside a string:
>>- Use __backslash__ before the quote
>>- Use __Double Quotation__ for Single quotes and vise versa.
>>```php
>>echo 'Joe's Invoice'; // ERROR!
>>
>>echo "Joe's Invoice";
>>echo 'Joe\'s Invoice';
>>```


> [!info] Variables
> __Variables__ starts with a dollar sign `$`
> ```php
> $name = 'Gio';
> 
> echo $name;
> ```
> 
>> [!abstract] Variable Names
>> Variable names __CANNOT__ start with:
>> - Numbers `$1name`
>> - Special characters (except: Underscore `_`)
>> ```php
>> $_123name = 'Gio';
>> 
>> echo $_123name;
>> ```
>> 
>>> [!danger] `$this`
>>> `this` refers to an object,
>>> so we'll get an error if name a variable `$this`
>
>> [!tip] Variables are assigned by ___value___
>> `$y` is __not referencing__ `$x`, it assigned __it's value__
>> ```php
>> $x = 1;
>> $y = $x;
>> 
>> $x = 3;
>> 
>> echo $y; // 1
>> ```
>> 
>> To assign by __REFERENCE__,
>> Add an __Ampersand `&`__:
>> ```php
>> $x = 1;
>> $y = &$x;
>> 
>> $x = 3;
>> 
>> echo $y;
>> ```
>
>
>> [!abstract] Ways to print a `string` with __Variable__
>> ```php
>> $firstName = 'Gio';
>> 
>> // Double Quotation (" ")
>> echo "Hello $firstName";
>> echo "Hello {$firstName}";
>> 
>> // Concatenation operator dot ( . )
>> echo 'Hello ' . $firstName; 
>> ```


> [!abstract] PHP Inside of HTML
> ```php
> <!DOCTYPE html>
> <html>
> 	<body>
> 		<h1>
> 			<?php 
> 				$x = 10;
> 				$y = 5;
> 				
> 				echo $x . ', ' . $y;
> 				// printing an html paragraph inside php (not advisable)
> 				echo '<p>' . $x . ', ' . $y . '</p>';
> 			?>
> 			<?= 'Hello World' ?>
> 		</h1>
> 		<p>My first paragraph.</p>
> </html>
> ```


