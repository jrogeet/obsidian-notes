---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info] Interface
> - Interface tells __WHAT NEEDS TO BE DONE__
> - but ___DOESN'T TELL the IMPLEMENTATION on HOW IT'S NEED TO BE DONE___
>> [!example]
>> Non-Technical Example:
>> ![[Pasted image 20240328181217.png]]
>> - There's different __Debt Collectors__
>> 	- with ___Different Method of `COllecting Money`___
>> - You don't care __HOW they COLLECT THE MONEY__
>> 	- As long as, you GET THE MONEY, or a portion of it.

> [!abstract] Interface Rules
 > - __ALL `METHODS`__ within ___Interface___ __MUST BE `PUBLIC`__
> - ALL `Methods` within the ___INTERFACE___ __MUST BE IMPLEMENTED__ to the class that __implements__ that ___interface___
> - ___Intefaces___ CANNOT HAVE `Properties`
> 	- but IT CAN HAVE __CONSTANTS__

> [!info] Polymorphism
> - Means __Many Forms__
> - An `Object` is considered __Polymorphic__ if it __CAN PASS MULTIPLE INSTANCES__ 
> - Which indicates that it can take many forms

> [!example] 
> _Index.php_
> ```php
> require_once __DIR__ . '/../vendor/autoload.php';
> 
> $collector = new \App\CollectionAgency();
> 
> echo $colector->collect(100) . PHP_EDL;
> ```
> _DebtCollector.php_
> ```php
> namespace App;
> 
> interface DebtCollector
> {
> 
> 	public function __construct();
> 	public function collect(float $owedAmount): float;
> }
> ```
> 
> _DebtCollectorService.php_
> ```php
> namespace App;
> 
> class DebtCollectionService
> {
> 	public function collectDebt(DebtCollector $collector)
> 	{
> 		$owedAmount = mt_rand(100, 1000);
> 		$collectedAmount = $collector->collect($owedAmount);
> 		
> 		echo 'Collected $' . $collectedAmount . ' out of $' . $owedAmount . PHP_EDL;
> 	}
> 
> }
> ```
> _CollectionAgency.php_
> ```php
> namespace App;
> 
> class CollectionAgency implements DebtCollector
> {
> 	public function collect(float $owedAmount): float
> 	{
> 		$guaranteed = $owedAmount * 0.5;
> 		
>		return mt_rand($guaranteed, $owedAmount);	
> 	}
> }
> ```
> 
> _Rocky.php_
> ```php
> namespace App;
> 
> class Rocky implements DebtCollector
> {
> 	public function collect(float $owedAmount): float
> 	{
> 		
> 		
>		return $owedAmount * 0.65;	
> 	}
> }
> ```
> - Multiple `Interfaces` can be Implemented
> - `mt_rand` generates a random number
> 	- `mt_rand(minimum, maximum);`

> [!tip] ___Interface___ can also __Extend__
> ```php
> namespace App;
> 
> interface DebtCollector extends AnotherInterface, SomeOtherInterface
> {
> 	public function __construct();
> 	pubic function collect(float $owedAmount): float;
> }
> ```
> - `Concrete Class` will need to __Implement__ all the `methods` from the ___Interface___ and it's __Extensions__




