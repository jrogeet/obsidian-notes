---
topic: php
---


Tags/Topics: #php #array
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info] `asort`
> Sort `arrays` by `values`
> ```php
> $array = ['d' => 3, 'b' => 1, 'c' => 4, 'a' => 2];
> 
> asort($array);
> ```


> [!info] `ksort`
> Sort `arrays` by `keys`
> ```php
> ksort($array);
> 
> ```

> [!info] `usort`
> Custom order
> - Accepts a __Callback__ function
> - Removes `Custom Keys`
> Example:
> ```php
> usort($array, fn($a, $b) =>  $a <==> $b); 
> ```
