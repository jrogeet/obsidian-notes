---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
- `Property` inside a __Trait__ can be used:
	- IN THE __TRAIT__
	- and the `Class` that uses the __Trait__

```php
namespace App;

trait LatteTrait
{
	protected string $milkType = 'whole-milk';

	public function makeLatte()
	{
		echo static::class . ' is making latte with' . $this->milkType . PHP_EOL;
	}
}
```

> [!example]
> In some code, others use `properties` ___not defined___ inside the `trait`
> like doing  `$this->milkType` __WITHOUT DEFINING__ it inside the `trait`
> 
> _Trait File_:
> ```php
> namespace App;
> 
> trait LatteTrait
> {
> 	public function makeLatte()
> 	{
> 		echo static::class . ' is making latte with ' . $this->milkType . PHP_EOL;
> 	}
> }
> ```
> 
> _Class that uses the Trait above_:
> ```php
> namespace App;
> 
> class LateMaker extends CoffeeMaker
> {
> 	use LatteTrait;
> 	
> 	private string $milkType = 'whole-milk';
> }
> ```

