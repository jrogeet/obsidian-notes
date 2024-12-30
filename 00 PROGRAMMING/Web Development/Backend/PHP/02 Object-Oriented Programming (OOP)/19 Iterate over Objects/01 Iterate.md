---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!info]
> `foreach` can also __iterate__ over the `properties` of an `Object`
> ```php
> namespace App;
> 
> class Invoice 
> {
> 	public string $id;
> 	
> 	public function __construct(public float $amount)
> 	{
> 		$this->id = random_int(10000, 9999999);	
> 	}
> }
> ```
> 
> ```PHP
> foreach(new App\Invoice(25) as $key => $value) {
> 	echo $key . ' = ' . $value . PHP_EOL;
> }
> ```
> ___OUTPUT___: 
> ![[Pasted image 20240330075226.png]]

> [!example]
> ```php
> $invoiceCollection = new InvoiceCollection([new \App\Invoice(15), new \App\Invoice(25), new \App\Invoice(50)]);
> 
> foreach($invoiceCollection as $invoice) {
> 	echo $invoice->id . ' - ' . $invoice->amount . PHP_EOL;
> }
> ```
> 
> - `\Iterator` Interface:
> ```php
> namespace App;
> 
> class InvoiceCollection implements \Iterator
> {
> 	public function __construct(public array $invoices)
> 	{
> 			
> 	}
> }
> ```

