---
topic: css
---
Tags/Topics: #css
∗:

---
# Flexbox

--- 
__One-dimensional__ CSS layout that can control the way items are spaced out and aligned within a container.

```css
display: flex;
```

This will make an element a __Flex Container__
- Any direct children of a flex container are called __Flex Items__.
![[Pasted image 20231031100706.png]]
>[!abstract] Flex Container
>___gap: 0___ | `<length>`
> - To create __space between items,__ without using margin
>
>___justify-content: flex-start___ | `flex-end` | `center` | `space-between` | `space-around` | `space-evenly` 
> - To align items along main axis (__horizontally,__ by default)
> 
> ___align-items: stretch___ | `flex-start` | `flex-end` | `center` | `baseline`
> - To align items along cross axis(__vertically__, by default)
>   
>___flex-direction: row___ | `row-reverse` | `column` | `column-reverse`
>   - To define which is the __main axis__
>   
> ___flex-wrap: nowrap___ | `wrap` | `wrap-reverse` 
>   - To allow items to __wrap into new line__ if they are too large
>
>___align-content: stretch___ | `flex-start` | `flex-end` | `center` | `space-between` | `space-around`
> - Only applies when there are __multiple lines__ (flex-wrap: wrap)

>[!abstract] Flex Items
> ___align-self: auto___ | `stretch` | `flex-start` | `flex-end` | `center` | `baseline`
> - To __overwrite__ align-items for individual flex items
> 
>___flex-grow: 0___ | `< integer >`
> - To allow an element __to grow__ (0 means no, 1+ means yes)
> 	- Expand the size of the element to occupy the available spaces
>   
>___flex-shrink: 1___ | `< integer > `
>   - To allow element __to shrink__ (0 means no, 1+ means yes)
>     
>___flex-basis: auto___ | `< length >`
>    - To define an item's width, __instead of the width__ property
>    
>___flex: 0 1 auto___ | `<int> <int> <len>`
>    - __Recommended__ shorthand for flex-grow, -shrink, -basis
>
>___order: 0___ | `<integer>`
> - Controls order of items, -1 makes item __first__, 1 makes it __last__

>[!Example] Flex Property (`flex`,`flex-grow`, `flex-shrink`, `flex-basis`)
>```css
>flex: `<flex-grow>`, `<flex-shrink>`, `<flex-basis>`
>flex: 0 0 200px;
>```
>Flex Basis:
>resize the width of Flex Items but still within the parent container
>```css
>flex-basis: 100px;
>
>/* Default*/
>flex-basis: auto;
>```
>
>Flex Shrink:
>```css
>flex-shrink: 0;
>
>/*Default:*/
>flex-shrink: 1;
>```


>[!tip] Flexbox has a main and cross axis.
>`flex-direction` property
>- `row` (default): _horizontal axis_ with flex items __from left to right__.
>- `row-reverse`: _horizontal axis_ with flex items __from right to left.__
>- `column`: ___vertical axis___ with flex items from __top to bottom__.
>- `column-reverse`: ___vertical axis___ with flex items from __bottom to top__

>[!tip] `flex-wrap`
>Determines how ___flex items___ behave when the ___flex container___ is __too small__.
> - `flex-wrap: wrap;` Allow the items to wrap to the __next row__ or __column__.
> - `flex-wrap: nowrap;` (default) will prevent items from wrapping and shrink if needed.

>[!tip] `justify-content`
>Determines how the items inside a ___flex container___ are __positioned__ along the main axis, affecting their _position and the space around them_.
> - `justify-content: center;`

>[!tip] `align-items`
>Positions the ___flex content___ along the cross axis.
>If `flex-direction: row;`(set to row), the cross axis would be __vertical__