---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# 03 Strict Mode

--- 
```javascript
"use script";

// the code works the modern way
```
`"use strict"` can be enabled in a __function only__, by putting it in the beginning of a function.

>[!caution] Ensure that `"use strict"` is at the top
>__Strict mode__ will not enable, if its not on top of the script
>```javascript
>alert("some code");
>// "use strict" below is ignored -- it must be at the top
>
>"use strict";
>
>// strict mode is not activated
>```
>- Only _comments_ appear above `"use strict"`


>[!tip]
>- Strict mode helps us by giving more information about bugs and errors.
>- Strict mode reserves certain keywords that we can't use as variables, such as:
>	- `interface`
>	- `private`
>	- etc.

