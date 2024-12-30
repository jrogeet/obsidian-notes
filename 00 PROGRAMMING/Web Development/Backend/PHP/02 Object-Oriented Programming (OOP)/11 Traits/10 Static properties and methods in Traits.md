---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!info]
> ```php
> namespace App;
> 
> trait LatteTrait
> {
> 	public static int $x = 1;
> 	
> 	public static function foo()
> 	{
> 		echo 'Foo Bar' . PHP_EOL;
> 	}
> 	
> }
> ```
> 
> ```php
> \App\LatteMaker::foo();
> echo \App\LatteMaker:: $x;
> ```

