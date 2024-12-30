---
topic: php
---


Tags/Topics: #php #operators
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info] 
> __Supresses Any Error__ from an Expression.
> ```php
> $x = file('foo.txt'); // ERROR: file not found
> 
> $x = @file('foo.txt'); //
> ```
> - NOT Recommended to use
