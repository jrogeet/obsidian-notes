---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
- Including both inside a __Curly braces__:
```php
use PaymentGateway\Paddle\{Transaction, Customer Profile};

$paddleTransaction = new Transaction();
$paddleCustomerProfile = new CustomerProfile();
```
- Or just straight importing the `namespace`:
```php
use PaymentGateway\Paddle;

$paddleTransaction = new Paddle\Transaction();
$paddleCustomerProfile = new Paddle\CustomerProfile();
```