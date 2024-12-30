---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!tip] METHOD PRECEDENCE
> 1. __Class__ `method`
> 2. __Trait__ `method`
> 3. __Parent Class__ `method`
> 
> ```php
> class CappucinoMaker extends CoffeeMaker
> {
> 	use CappuccinoTrait; // also has makeCappuccino() method
> 	
> 	public function makeCappuccino()
> 	{
> 		echo 'Making Cappuccino (UPDATED)' . PHP_EOL;
> 	}
> }
> ```
> 