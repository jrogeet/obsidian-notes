---
topic: php
---


Tags/Topics: #php #files
∗:[[0 PHP|PHP]]

---
# Design

--- 

#### include & require
```php
include 'file.php';

require 'file.php';
```

Difference is that IF THERE'S A PROBLEM,  
`include` result to a __WARNING__,
- means the __code below IT will still run__
`require` results in an ___ERROR___.
- the program will ___stop in the `require` line___.


#### include_once & require_once
```php
include_once 'file.php';

require_once 'file.php';
```

Only includes the file, if it isn't already.

>[!example]
>```php
>require_once 'file.php'; // $x = 5;
>
>$x++;
>
>echo $x . '<br />';
>
>require_once 'file.php'; // should have bring $x back to 5 but NO
>
>echo $x . '<br />';
>
>echo 'Hello World';
>
>// OUTPUT:
>// 6
>// 6
>// Hello World
>```

---

> [!info] Return value of include using `return`
> ```php
> $y = include 'file.php';
> $z = include 'non-existent-file.php';
> 
> var_dump($y); // int(1)
> 
> var_dump($z); // WARNING and bool(false)
> ```
>> [!tip] Getting the content of HTML
>> ```php
>> ob_start();
>> include './partials/nav.php';
>> $nav = ob_get_clean();
>> 
>> var_dump($nav); // string( ) then the content of the html
>> echo $nav; // print the html content
>> ```
>
>
>> [!tip] Changing HTML Content:
>> ```php
>> ob_start();
>> include './partials/nav.php';
>> $nav = ob_get_clean();
>>
>>// ALTER CONTENT:
>> $nav = str_replace('About', 'About Us', $nav);
>> ```




> [!tip] Code re-Usability
> Using `include` in HTML
> ```php
> <!DOCTYPE html>
><html>
>	<head>
>		<title> Home Page </title>
>	</head>
>	<body>
>		<?php include './partials/nav.php' ?>
>		<h1> Home </h1>
>		<p>Hello from the Home page! </p>
>	</body>
></html>
> ```
