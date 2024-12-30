## CSS NOTES
***
Inline CSS -
```html
<h1 style="color: blue">
</h1>
```
Internal CSS - 
```html
<style>
 h1{
	 color: blue;
 }
</style>
```
External CSS - From a .CSS file linked to the HTML file


***
#### Using Margins and Paddings
```css
.main-header {
	padding: 20px;       //PADDING ALL SIDES
	padding-left: 40px;  // PADDING LEFT ONLY
	padding-right: 40px; // PADDING RIGHT ONLY
}
```


SHORTHAND is when we specify multiple values for one property.
>The FIRST value is for the padding for TOP&BOTTOM 
The SECOND value is for the padding for LEFT&RIGHT
```css
.main-header {
	.padding: 20px 40px;
}
```

another example:
We want some space between each list so we put margin at the bottom of each li elements, but we don't want to put some space at the end of the list.
```css
li {
	margin-bottom: 10px;
}

li:lastchild {
	margin-bottom: 0;
}
```

If two elements'  margin collapse or is on top of each other, the two margins will NOT add up. Simply the LARGEST margin will apply.

      For example: ul has 15 and h3 has 40 it will not become  
         55 px, its only 40px.
```css
ul {
	margin-bottom: 15px;
}

h3 {
	margin-top: 40px;
}
```
***
#### DIMENSIONS
The "height: auto;" only works if the height is already specified before.
```css
.post-img {
	width: 300px;
	height: auto;
}
```
***
#### CENTERING THE PAGE
We use div for the whole content of the page and named it container.
```html
<body>
<div class="container">

</div>
</body>
```
To center the page:
```css
.container {
	width: 700px
	
	margin-left: auto;
	margin-right: auto;
	OR
	margin: 0 auto;
}
```