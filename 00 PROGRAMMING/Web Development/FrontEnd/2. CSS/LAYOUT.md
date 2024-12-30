### LAYOUT
<ul>
<li>is the way text, images and other content is placed and arranged on a webpage.</li>
<li>Layout gives the page a visual structure, into which we place our content</li>
<li><b>Building a layout:</b> arranging page lements into a visual structure, instead of simply having them placed one after another (normal flow)</li>
</ul>


![[Pasted image 20220813100917.png]]
![[Pasted image 20220813102000.png]]

***
#### FLOAT

We can see that the text element start from behind the image.
![[Pasted image 20220813110558.png]]
```css
.author-img {
    float: left;
}

.author{
    padding-left: 10px;
}
```
If we add more, we can see that the image isn't affected by the padding, like it's out of the page's flow.
![[Pasted image 20220813110340.png]]
```css
.author-img {
    float: left;
}

.author{
    padding-left: 80px;
    padding-top: 10px;
}
```

![[Pasted image 20220813111016.png]]

```css
.author-img {
    float: left;
}

.author{
    padding-left: 10px;
    padding-top: 10px;
    float: right;
}
```

#### ABSOLUTE POSITIONING vs. FLOATS
NORMAL FLOW 
<ul>
<li>Default positioning</li>
<li>Element is "in flow"</li>
<li>Elements are simply laid out according to their order in the HTML Code</li>
</ul>


Default positioning
```css
	position: relative;
```

ABSOLUTE POSITIONING
<ul>
<li>Element is removed from the normal flow: "out of flow"</li>
<li>No impact on surrounding elements, might overlap them</li>
<li>We use top, bottom, left, or right to offset the element from its relatively positioned container</li>
</ul>


```css
	position: absolute;
```
FLOATS
<ul>
<li>Element is removed from the normal flow: "out of flow"</li>
<li>Text and inline elements will wrap arround the floated element</li>
<li>The container will not adjust its height to the element</li>
</ul>


```css
	float: left;
	float: right;
```

#### How to Clear Floats

**#1 Clear**

![[Pasted image 20230330180543.png]]

First we create an empty div name `clear` (ofc you can put whatever name you want)
![[Pasted image 20230330180656.png | 350]]
First, we select it by typing `.clear{` then put `clear: ;`
If you want to clear the left then put `clear: left;` then `clear: right;` if right. but here we want to clear both left and right so we put `clear: both;`
![[Pasted image 20230330180835.png]]
![[Pasted image 20230330181007.png]]


**#2 Clearfix hack**

Instead of the first method which will need to manually add a div element in the html file we can do this.


![[Pasted image 20230330181413.png]]
First, we add the `clearfix` name in the `main-header` class
![[Pasted image 20230330181808.png]]
then we will call it in the css file, then put `::after` pseudo-element after it.

What this do is add or create a new element which will be the less child element of the container. Doing this is exactly the same as adding a `<div class="clear">`.

![[Pasted image 20230330182056.png]]
It only appears if we define something for the content property.
`content: '';` this will be empty text.

![[Pasted image 20230330182208.png]]
And also by Default pseudo-elements like `after` and `before` are **INLINE ELEMENTS** . However clearing floats like this only really works on a block-level element. and so we set the `display` property to `block`.

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
