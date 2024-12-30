---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!caution]
> When declaring a `variable`, `constant`, `functions`, or `classes`, It automatically stores in the ___Global scope___.
> - This could result to an ___ERROR___ when `names` are used more than once.

>[!info] NameSpace
> - Is like a __Virtual Directories__
> - Groups `variable`, `constant`, `function` and `classes`


> [!example]
> 
> ```php
> declare(strict_types = 1);
>
>namespace Bayaran;
>
>class Transaction
>{
>
>}
>```
>
>_In another file_:
>```php
>require_once '.../PaymentGateway/Paddle/Transaction.php';
>
>var_dump(new Bayaran\Transaction);
>```
>---
>---
>---
>
>```php
>declare(strict_types = 1);
>
>namespace PaymentGateway\Stripe;
>
>class Transaction
>{
>
>}
>```
>
>```php
>declare(strict_types = 1);
>
>namespace PaymentGateway\Paddle;
>
>class Transaction
>{
>}
>```
>
>
>```php
>require_once '.../PaymentGateway/Stripe/Transaction.php'
>require_once '.../PaymentGateway/Paddle/Transaction.php'
>require_once '.../PaymentGateway/Paddle/CustomerProfile.php'
>
>var_dump(new PaymentGateway\Strip\Transaction());
>```

> [!tip] `use` keyword to Import `namespace`
> ```php
>require_once '.../PaymentGateway/Stripe/Transaction.php'
>require_once '.../PaymentGateway/Paddle/Transaction.php'
> 
> use PaymentGateway\Stripe\Transaction;
> 
> new Transaction();
> ```


