---
topic: php
---


Tags/Topics: #php #datatypes 
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!abstract] Quotation Marks
> - __Double Quotes__ (`" "`): Can store `variables`
> - ___Single Quotes___ (`' '`): CAN'T  
> ```php
> $firstName = 'Will';
> $lastName = "$firstName Smith";
> 
> // Curly braces for better readability
> $lastName = "${firstName} Smith";
> $lastName = "{$firstName} Smith";
> ```

>[!tip] Accessing single characters
>```php
>$firstName = 'Will';
>$lastName = 'Smith';
>
>$name = $firstName . ' ' . $lastName;
>
>echo $name[0]; // W
>echo $name[1]; // i
>echo $name[-2]; // t
>```
>
>> [!info] Modifying strings
>> ```php
>> $name[0] = 'R'; // Rill Smith
>> $name[-2] = 's'; // Rill Smish
>> 
>> var_dump($name); // string(10) "Will Smith"
>> 
>> 
>> // Putting Index number more than the length
>> $name[15] = 'I';
>> var_dump($name); //  string(16) "Will Smith I"
>> ```

>[!abstract] Heredoc & Nowdoc
>
>> [!tip] Use-case:
>> For __Multi-line Strings__ without needing to use `Quotation Marks (" ")`
>
>
>__Heredoc__:  same as __Double-quotation Strings__ `" "` (Can store `variables`)
>```php
>$x = 1;
>$y = 2;
>$text = <<<TEXT
>Line 1 $x
>Line 2 $y
>Line 3
>TEXT;
>
>$textB = <<< TEXTB
><div>
>	<p>Hello World</p>
></div>
>TEXTB;
>
>echo nl2br($text); // Inserts new line 
>```
> - `TEXT` is the __Identifier__
> 
> ___Nowdoc___: Same as ___Single-quotation Strings___ `' '` (CANNOT store `variables`)
> ```php
> $text = <<< 'TEXT'
> Line 1
> Line 2
> Line 3
> TEXT;
> 
> echo nl2br($text);
> ```
> 
>> [!important] 
>> Any space in either __Heredoc__ or ___Nowdoc___ are rendered, even if you can't see it in the browser
>> ```php
>> $text = <<<TEXT
>> 	Hello World // Adds 4 spaces
>> TEXT;
>> 
>> var_dump($text); // string(15) "Hello World"
>> ```
