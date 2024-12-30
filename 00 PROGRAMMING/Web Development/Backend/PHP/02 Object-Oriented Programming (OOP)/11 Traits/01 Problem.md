---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
>[!caution] Diamond Problem
>![[Pasted image 20240329080559.png]]
> - `All in One Coffee Maker` doesn't know __WHICH `makeCoffee` METHOD TO RUN__

_CoffeeMaker.php_
```php
namespace App;

class CoffeeMaker
{
	public function makeCoffee()
	{
		echo static::class . ' is making coffee' . PHP_EOL;
	}
}
```

_LatteMaker.php_
```php
namespace App;

class LatteMaker extends CoffeeMaker
{
	public function makeLatte()
	{
		echo static::class . ' is making latte' . PHP_EOL;
	}
}
```

_CappuccinoMaker.php_
```php
namespace App;

class CappuccinoMaker extends CoffeeMaker
{
	public function makeCapuccino()
	{
		echo static::class . ' is making cappucino' . PHP_EOL;
	}
}
```

_AllInOneCoffeeMaker.php_
```php
namespace App;

class AllInOneCoffeeMaker
{
	
}
```

_Index.php_
```php
$coffeeMaker = new \App\CoffeeMaker();
$coffeeMaker->makeCoffee();

$latteMaker = new \App\LatteMaker();
$latteMaker->makeCoffee();
$latteMaker->makeLatte();
```

---
##### __Interfaces__ instead of ___Multiple Inheritance___

- __Interfaces__ is GOOD if the _IMPLEMENTATION IS DIFFERENT_
- NOT when you only ___DUPLICATING___ the `code`
_AllInOneCoffeeMaker.php_
```php
namespace App;

class AllInOneCoffeeMaker extends CoffeeMaker implements MakesLatte, MakesCappuccino
{
	public function makeLatte()
	{
		echo static::class . ' is making latte' . PHP_EOL;
	}
	
	public function makeCapuccino()
	{
		echo static::class . ' is making cappucino' . PHP_EOL;
	}
}
```

_Index.php_
```php
$coffeeMaker = new \App\CoffeeMaker();
$coffeeMaker->makeCoffee();

$latteMaker = new \App\LatteMaker();
$latteMaker->makeCoffee();
$latteMaker->makeLatte();
```






