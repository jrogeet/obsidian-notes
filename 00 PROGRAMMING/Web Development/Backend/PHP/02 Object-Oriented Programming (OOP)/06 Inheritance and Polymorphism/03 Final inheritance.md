---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
#### Final `Class`/`Method`

> [!INFO] FINAL `class` and `method`
> Define `Class`/`Method` as __FINAL__
> - CANNOT BE INHERETED OR EXTENDED
> ```php
> final class Toaster {
> 	// ...
> }
>
> // IN ANOTHER FILE:
> class ToasterPro extends Toaster
> {
>	// THIS WOULD RESULT TO A FATAL ERROR!
>}
>
> ```
