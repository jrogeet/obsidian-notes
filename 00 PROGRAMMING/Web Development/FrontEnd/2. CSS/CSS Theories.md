#### CONFLICTING DECLARATION
If there is multiple Selectors such as Class(.) or pseudo-class(:) selectors, ID (#) selectors, Element selector(p,div,li etc.) 
```css
.author{
	font-style: italic;
	font-size: 18px;
}

#author-text{
	font-size: 20px;
}

p,li{
	font-family: sans-serif;
	color: #444444;
	font-size: 22px;
}
```
Highest Priority(1) - Lowest Priority(4)
1. ID(#) Selector
2. Class(.) or pseudo-class(:) selectors
3. Element selector(p, div, li etc.)
4. Universal selector(*)

***
#### INHERITANCE
Inheritance is what happen when a parent element's selector has a property that also applies to the child elements.
for ex:
> As we can see, body is a parent element so when we put values in it, it will get passed down to it's child elements.
```css
body{
	color: #444;
	font-size: 16px;
	font-family: sans-serif;
	
	border-top: 10px solid #1098ad;
}

p{
	text-transform: uppercase;
}

h1, h2, h3{
	color: #1098ad
}
```
>  So the property "color: #444;" will apply/inherit to all the child selectors like "p{}" for example, BUT in "h1, h2, h3" it will get overwritten since they declare another property Color.
> Not every property will get applied to every child elements/selector. The color, font-size, and font-family will get inherited by the text child, EXCEPT the "border-top" property, It will simply add a border to the top of the site. It depends on the property.
***
#### UNIVERSAL Selector (*)
Applies to all elements and there's no inheritance involved.
Universal selector has the Lowest Priority.
```css
* {
	border-top: 10px solid #1098ad;
}

body{
	color: #444;
	font-size: 16px;
	font-family: sans-serif;
	
	/*border-top: 10px solid #1098ad;*/
}
```
***

### CSS BOX MODEL

1. Content - Text, Images, Table, Video etc. Using CSS Properties we can specify the height or the width of the content area
2. Border - A line around the element, still **inside** of the element.
3. Padding - Invisible space/White space around the content, **inside** of the element. Between the Content and the Border.
4. Margin - Space **outside**of the element, between elements
5. Fill area - Area that gets filled with **background color** or **background image**
![[Pasted image 20220801182304.png | 600]]

EXAMPLE:
![[Pasted image 20220801192446.png| 900]]


However, the implied height and width (content) is NOT the final sizes of the element because the border and the padding also taken into account.

>   <b>FINAL ELEMENT WIDTH</b> = left border + left padding + width + right padding + right border

 >  <b>FINAL ELEMENT HEIGHT</b> = top border + top padding + height + bottom padding + bottom border
 


***
### Types of Boxes
<b>Inline boxes</b> - Boxes which only occupies space that needed for the content. (Ex: Image, Anchor tags/Links etc.)
<ul>
	<li>Occupies only the space <b>necessary for its content</b></li>
	<li>Causes <b>no line-breaks</b> after or before the element</li>
	<li>Box model applies in a different way: <b>heights and widths do not apply</b></li>
	<li><b>Paddings and margins</b> are applied <b>only horizontally</b> (Left and Right)</li>
</ul>

For INLINE ELEMENTS, width and height properties don't have effect. Paddings and Margins are only applied HORIZONTALLY  (left and right).

> Default elements: a, img, strong, em, button, etc.

>Transform block to Inline
>With CSS: display: inline

![[Pasted image 20220806104659.png]]
![[Pasted image 20220806105431.png]]



 <b>Block-Level Elements/boxes </b> - Occupy all the space that they can and create line breaks after them or they can't be side-by-side with another. (Ex: Headings, paragraph etc.)
 <ul>
	 <li>Elements are formatted visually as <b>blocks</b> </li>
	<li>Elements occupy <b>100% of parent element's width</b>, no matter the content</li>
	<li>Elements are <b>stacked vertically</b> by default, one after another</li>
 </ul>    

> Default elements: body, main, header, footer, section, nav, aside, div, h1-h6, p, ul, ol, li, etc.

> We can transform INLINE box to BLOCK-LINE with:
> With CSS: display: block

![[Pasted image 20220806104641.png]]

![[Pasted image 20220806104738.png]]

INLINE-BLOCK BOXES - Looks like INLINE from the <b>outside</b>, behaves like BLOCK-Level on the <b>inside</b>

    IMAGES is INLINE-BLOCK Element
<ul>
	<li>Occupies only content's space</li>
	<li>Causes no line-breaks</li>
	<li>Box-model applies as showed</li>
</ul>

> display: inline-block;
***
### NORMAL FLOW vs. ABSOLUTE POSITIONING


###### NORMAL FLOW:
<ul>
<li>Default positioning</li>

```css
position: relative;
```

<li>Element is <b>"in flow"</b></li>
<li>Elements are simply laid out according to their order in the HTML code</li>
</ul>



###### ABSOLUTE POSITIONING:
<ul>
<li>Element is removed from the normal flow <b>"out of flow"</b></li>
<li>No impact on surrounding elements, might overlap them</li>
<li>We use top, bottom, left, or right to offset the  element from its <b>relatively positioned container.</b> </li>
</ul>

![[Pasted image 20220808185122.png]]

***
### PSEUDO-ELEMENTS
Elements that don't exist in the HTML, but we can still select and style in CSS. (Ex. First word/sentence of a paragraph)
```css
h1::first-letter {
	font-style: normal;
	margin-right: 5px;
}

p::first-line {
	color: red;
}
```
###### ADJACENT SIBLING SELECTOR
An element that is part of the same parent. Adjacent sibling is the element that comes after it.
```css
h3 + p::first-line {
    color: red;
}
```
###### BEFORE & AFTER PSEUDO-ELEMENTS
Before - will become the very first child element.
AFTER - will be the last child element.
```css
h2 {
    position: relative;
}

h2::after {
    content: "TOP";
    background-color: yellow;
    color: #000;
    font-size: 16px;
    font-weight: bold;
    display: inline-block;
    padding: 5px 10px;
    position: absolute;
    top: -10px;
    right: -25px;
}
```

#### BOX-MODEL with BOX-SIZING: BORDER-BOX
Instead of changing the width manually, we can use `box-sizing: border-box;` and it will automatically do it. 
For example, we set the `width: 300px;` then set `padding: 40px;` it will add the `40px` to the `300px` which would be `380px` width in total ruining the layout.
![[Pasted image 20230330194914.png | 450]]
![[Pasted image 20230330195049.png]]

But with `box-sizing: border-box;` 
![[Pasted image 20230330195143.png | 550]]
![[Pasted image 20230330195209.png]]
The `width` automatically adjusted to make it `300px` still.


![[Pasted image 20230330193719.png | 350]]

> **Final element width** = right border + right padding + width + left padding + left border
> **Final element height** = top border + top padding + height + bottom padding + bottom border

```css
example {
	box-sizing: border-box;
}
```

![[Pasted image 20230330194051.png | 600]]

![[Pasted image 20230330194229.png]]
