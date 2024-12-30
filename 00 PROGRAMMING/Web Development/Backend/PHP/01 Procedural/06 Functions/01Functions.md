---
topic: php
---


Tags/Topics: #php #functions
∗:[[0 PHP|PHP]]

---
# Design

--- 
`functions` can be defined __everywhere__ (top, bottom etc.)
```php
function name() {
	echo 'Hello ';
	return 'World'
}

echo name();
```

#### Except:
- if it's inside a CONDITIONAL:
```php
var_dump(foo()); // Undefined ERROR

if (true) {
	function foo()
	{
		return 'Hello World';
	}
}

var_dump(foo()); // WORKS!
```

- if it's __inside a function__ and the `Outer Function` didn't get called first.
```php
foo(); // WORKS! 'Foo'
bar(); // WORKS! 'Bar'

// below will cause an UNDEFINED ERROR:
// not calling foo()
bar(); // ERROR!

function foo()
{
	echo 'Foo';
	function bar() {
		echo 'Bar';
	}
}
```

---
__FUNCTIONS CAN'T HAVE THE SAME `NAME`__
```php
function foo()
{
	echo 'Foo';
	function bar() {
		echo 'Bar';
		
		function foo() { // FATAL ERROR: Cannot re-declare foo()
			echo 'Foo 2';
		}
	}
}
```

> [!tip] Specify the `data type` of the return value:
> Add a _colon_ and the __data type__:
> function name()`: int`
> 
> ```php
> function foo(): int {
> 	return '1';
> }
> 
> var_dump(foo()); // int(1)
> ```
> however, THIS WOULD'NT WORK with `strict_types` ENABLED.
> ```php
> declare(strict_types=1); // add this to the top of the code above and it will cause an ERROR
> ```
> 
>> [!INFO] Not returning anything
>> `: void`
>> ```php
>> function foo(): void {
>> 	return;
>> 	// return null; --- This would cause an ERROR since you're actually RETURNING SOMETHING (null) which is not void 
>> }
>> 
>> var_dump(foo()); // NULL
>> ```
>
>
>> [!abstract] Expect a `data type` BUT also __ACCEPT__ `null`
>> Add a __Question Mark__ `?` before the `data type`
>> ```php
>> function foo(): ?int {
>> 	return null;
>> }
>> 
>> var_dump(foo()); // NULL
>> ```
>
>
>> [!ABSTRACT] __MULTIPLE__ Data Types:
>> Pipe separator `|`
>> ```php
>> function foo(): int|float|array {
>> 	return [1.5];
>> }
>> ```
>> Or, `: mixed`
>> ```php
>> function foo(): mixed {
>> 	return [1.5];
>> }
>> 
>> var_dump(foo());
>> ```




