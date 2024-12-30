---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

#### Composition
![[Pasted image 20240328133233.png]]
>[!info] COMPOSITION
>Instead of ___EXTENDing___ `ToasterPro`,
>We can use a __COMPOSITION__:
>
>So that _FancyOver_ will have `ToasterPro`'s __Functionality__.
>
>_FancyOven.php_
>```php
>namespace App;
>
>class FancyOver
>{
>
>// COMPOSITION
>	private ToasterPro $toaster;
>
>	public function fry(ToasterPro $toaster)
>	{
>		$this ->toaster = $toaster;
>	}
>	
>	// OR with Property Promotion:
>	public function __construct(private ToasterPro $toaster)
>	{
>	}
>	
>	public function fry()
>	{
>		// fry stuff
>	}
>	
>	
>	public function toast()
>	{
>		$this->toaster->toast();
>	}
>	
>	public function toastBagel()
>	{
>		$this->toaster->toastBagel();
>	}
>}
>```
