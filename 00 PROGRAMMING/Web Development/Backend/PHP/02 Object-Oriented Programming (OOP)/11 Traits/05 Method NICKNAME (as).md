---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!TIP] Ali`as`
> Set a _nickname_ for `trait methods`
> ```php 
> namespace App;
> 
> class AllInOneCoffeeMaker extends CoffeeMaker
> {
> 	use CappuccinoTrait ;
> 	
> 	use LatteTrait {
> 		LatteTrait::makeLatte as makeOriginalLatte;
> 	}
> }
> ```