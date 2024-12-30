---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!info] SAME NAME `Methods`
> `Methods` from the ___Parent___ `Class` with the SAME NAME as the ___Child `Class`___, gets __OVERRIDE__ by the ___Child `Method`___
> - BUT, they need to have the __SAME METHOD SIGNATURE__
> For example, this would result to a `FATAL ERROR!`
> ```php
> public function addSlice(string $slice): void
> {
> }
> ```
> 
> ```php
> public function addSlice(int $slice):void
> {
> }
> // OR the return value
> public function addSlice(STRING $slice): int
> {
> }
> ```
> THIS DOESN'T APPLY TO `__construct()` METHOD!




> [!example] `parent::__construct()`
> `__construct()` when appears on both `Class` files, 
> the ___Parent___ `__construct()` is __OVERWRITTEN__
> ```php
> class Toaster 
> {
> 	protected array $slices;
> 	protected int $size;
> 	
> 	public function __construct()
> 	{
> 		$this->slices = [];
> 		$this->size = 2;	
> 	}
> 	
> 	public function addSlice(string $slice): void
> 	{
> 		if (count($this->slices) < $this->size) {
> 			$this->slices[] = $slice;
> 		}	
> 	}
> }
> ```
> 
> ```php
> class ToasterPro extends Toaster
> {
> 	public function __construct()
> 	{
> 		parent::__construct();
> 		$this->size = 4;	
> 	}
> 	
> 	public function toastBagel()
> 	{
> 		// ...	
> 	}
> }
> ```
> - the `__construct()` method here is run instead of the one from the ___Parent `Class`___ 
> 	- with `parent::construct()` we run the one from the ___Parent `Class`___ first,
> 	- then Modified `size`
