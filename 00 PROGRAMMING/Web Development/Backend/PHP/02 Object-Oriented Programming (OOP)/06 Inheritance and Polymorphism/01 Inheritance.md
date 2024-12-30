---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
![[Pasted image 20240328085120.png]]

> [!example]
> - `Toaster`: Normal 2 Capacity
> ```php
> namespace App;
> 
> class Toaster;
> {
> 	public array $slices = [];
> 	public int $size = 2;
> 	
> 	public function addSlice(string $slice): void
> 	{
> 		if (count($this->slices) < $this ->size) {
> 			$this->slices[] = $slice;
> 		}
> 	}
> 	
> 	public function toast()
> 	{
> 		foreach ($this->slices as $i => $slice) {
> 			echo ($i + 1) . ' :Toasting ' . $slice . PHP_EDL;
> 		}
> 	}
> }
> ```
> Running it:
> ```php
> use App\Toaster;
> 
> require_once __DIR__ . '/../vendor/autoload.php';
> 
> $toaster = new Toaster();
> 
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->toast();
> ```
> __OUTPUT__:
> ```
> 1: Toasting bread
> 2: Toasting bread
> ```
> 
> ---
> 
> - `ToasterPro`: 4 Capacity, can do Bagels
> ```php
> namespace App;
> 
> class ToasterPro extends Toaster
> {
> 	public in $size = 4;
> 	
> 	public function toastBagel()
> 	{
> 		foreach ($this->slices as $i => $slice) {
> 		echo ($i + 1) . ' :Toasting ' . $slice .  ' with bagels option' . PHP_EDL;
> 	}
> }
> ```
> - `class ToasterPro` then `extends Toaster`
> 	- `ToasterPro` __Inherits EVERYTHING__ from the `Toaster` _Class_
> Running it:
> ```php
> use App\Toaster;
> use App\ToasterPro;
> 
> require_once __DIR__ . '/../vendor/autoload.php';
> 
> $toaster = new ToasterPro();
> 
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->toast();
> // Toasting with bagel
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->addSlice('bread');
> $toaster->toastBagel();
> ```
> __OUTPUT__:
> ```
> 1: Toasting bread
> 2: Toasting bread
> 3: Toasting bread
> 4: Toasting bread
> 1: Toasting bread with bagels option
> 2: Toasting bread with bagels option
> 3: Toasting bread with bagels option
> 4: Toasting bread with bagels option
> ```


> [!abstract] Rules
> - You can't __decrease__ the visibility of the `property` from the __Parent `Class`__
> 
> ```php
> class Toaster {
> 	public int $size = 2;
> 	 
> 	 //...
> }
> 
> // In another file:
> class ToasterPro extends Toaster
> {
> 	protected int $size = 4; // ERROR!
> 	
> 	// ...
> }
> ```
> but you CAN __INCREASE__ it's visibility:
> ```php
> class Toaster {
> 	protected int $size = 2;
> 	 
> 	 //...
> }
> 
> // In another file:
> class ToasterPro extends Toaster
> {
> 	public int $size = 4; // ERROR!
> 	
> 	// ...
> }
> ```

---

