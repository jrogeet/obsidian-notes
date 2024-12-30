---
topic: php
---


Tags/Topics: #php #controlstructure
∗:[[0 PHP|PHP]]

---
# Match Expression

--- 
> [!info] Difference between `Switch` and `Match` expression
> - `Switch` does ___LOOSE___ comparison
> - `Match` does __STRICT__ comparison


```php
$paymentStatus = 1;
```

>[!note] In `Switch` :
> ```php
>switch($paymentStatus) {
>	case 1:
>		echo 'Paid';
>		break;
>	case 2:
>	case 3:
>		echo 'Payment Declined';
>		break;
>		
>	case 0:
>		echo 'Pending Payment';
>		break;
>		
>	default:
>		echo 'Unknown Payment Status';
>}
> ```



> [!abstract] In `Match`:
> ```php
> match($paymentStatus) {
> 	1 => print 'Paid',
> 	2,3 => print 'Payment Declined',
> 	0 => print 'Pending Payment',
> }
> ```

> [!info] `Match`
> `Match` is an __EXPRESSION__ which __RETURNS A VALUE__.
> ```php
> $paymentStatusDisplay = match($paymentStatus) {
> 	1 => 'Paid',
> 	2, 3 => 'Payment Declined',
> 	0 => 'Pending Payment'
> };
> 
> echo $paymentStatusDisplay
> ```
