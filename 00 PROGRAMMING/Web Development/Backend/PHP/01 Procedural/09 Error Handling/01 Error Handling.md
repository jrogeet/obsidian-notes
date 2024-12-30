---
topic: php
---


Tags/Topics: #php #error
∗:[[0 PHP|PHP]]

---
# Design

--- 
https://www.php.net/manual/en/errorfunc.constants.php

```php
error_reporting(0); // Turn off reporting errors
error_reporting(E_ALL); // Enable all error reporting including warnings

error_reporting(E_ALL & ~E_WARNING);
```


>[!TIP] `trigger_error`
>User Error Constants
>```php
>trigger_error('Example error', E_USER_ERROR);
>```
