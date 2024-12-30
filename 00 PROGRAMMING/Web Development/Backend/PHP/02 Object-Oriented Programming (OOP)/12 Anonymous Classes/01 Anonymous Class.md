---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

---

> [!info] Anonymous Class
> ```php
> $obj = new class(1, 2, 3) {
> 	public function __construct(public int $x, public int $y, public int $z)
> 	{
> 			
> 	}
> }
> ```
> just like a Normal `Class`,
> It can do __Inheritance__, ___Interface___ and _Traits_
> ```php
> $obj = new class(1, 2, 3) extends MyClass implements MyInterface 
> {
> 
> 	Use MyTrait;
> 	
> 	public function __construct(public int $x, public int $y, public int $z)
> 	{
> 			
> 	}
> }
> ```

>[!tip] Type Hinting `Anonymous Class`
>```php
>$obj = new class(1, 2, 3) implements MyInterface 
>{
>	public function __construct(public int $x, public int $y, public int $z)
>	{
>	}
>};
>
>foo($obj);
>
>function foo(MyInterface $obj)
>{
>	var_dump($obj)
>}
>```

> [!tip] Nesting `Anonymous Classes`
> ```php
> namespace App;
> 
> class ClassA
> {
> 	public function __construct(public int $x, public int $y)
> 	{
> 	}
> 	
> 	public function foo(): string
> 	{
> 		return 'foo';	
> 	}
> 	
> 	public function bar(): object
> 	{
> 		return new class {
> 			
> 		}
> 	}
> }
> ```
> 
> ```php
> $obj = new ClassA(1, 2);
> 
> var_dump($obj->bar());
> ```
> - `Properties` and `Methods` of the __MAIN CLASS__ (`ClassA`) ___CANNOT BE ACCESSED___ by the _ANONYMOUS CLASS_ inside `bar()`
> ```php
> public function bar(): object
> {
> 	return new class {
> 		echo $this->y;
> 	}
> }
> ```

 
