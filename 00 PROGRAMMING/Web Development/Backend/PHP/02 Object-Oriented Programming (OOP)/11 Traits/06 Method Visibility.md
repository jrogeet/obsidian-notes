---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 


>[!tip] Change __Visibility__ of `trait methods`
>Setting a __Trait__ `method` private or protected,
>__CAN STILL BE USED by the `Class` that uses that `Trait`__
>but, NOT OUTSIDE OF IT.
>---
> - Change it's `visibility`
>```php
>class CappuccinoMaker extends CoffeeMaker
>{
>	use CappuccinoTrait {
>		CappuccinoTrait::makeCappuccino as public;
>	}
>}
>```
