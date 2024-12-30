---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!caution] `Method` __NAME__ conflict between `traits`
> If `traits` are used in a __Class__, and BOTH `traits` have a __METHOD with the SAME NAME__
> It wouldn't know which to run.
> 
>__USE `insteadof` to SPECIFY__
> ```php
> namespace App;
> 
> class AllInOneCoffeeMaker extends CoffeeMaker
> {
> 	use CappuccinoTrait;
> 	
> 	use LatteTrait {
> 		LatteTrait::makeLatte insteadof CappuccinoTrait;
> 	}
> }
> ```