---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!note]- Instead of:
>  _Trait File_:
> ```php
> namespace App;
> 
> trait LatteTrait
> {
> 	public function makeLatte()
> 	{
> 		echo static::class . ' is making latte with ' . $this->getMilkType() . PHP_EOL;
> 	}
> 	
> 	public function getMilkType(): string
> 	{
> 		if (property_exists($this, 'milkType')) {
> 			return $this->milkType;
> 		}
> 		
> 		return '';
> 	}
> 	
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

```PHP
namespace App;

trait LatteTrait
{
	public function makeLatte()
	{
		echo static::class . ' is making latte with ' . $this->getMilkType() . PHP_EOL;
	}
	
	abstract public function getMilkType(): string;
}
```

```php
namespace App;

class LatteMaker extends CoffeeMaker
{
	use LatteTrait;

	private string $milkType = 'whole-milk';

	public function getMilkType(): string
	{
		// Implement getMilkType() method.
		return $this->milkType;
	}

}
```

---
> [!tip] Alternative to using `abstract`
> ```php
> namespace App;
> 
> trait LatteTrait
> {
> 	private string $milkType = 'whole-milk';
> 	
> 	public function makeLatte()
> 	{
> 		echo static::class . ' is making latte with ' . $this->milkType . PHP_EOL;
> 	}
> 	
> 	public function setMilkType(string $milkType): static
> 	{
> 		$this->milkType = $milkType;
> 		
> 		return $this;
> 	}
> }
> ```
