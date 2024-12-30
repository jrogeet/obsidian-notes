While __Pseudo-classes__ uses One(1) Semi-colon `:`

___Pseudo-elements___ uses Two(2) Semi-colon `::`

```css
h1::first-letter {
	font-style: normal;
	margin-right: 5px;
}

p::first-line {
	color: red;
}
```

>[!example] Adjacent Siblings Pseudo-element
>Only the first line of the __paragraphs__ adjacent to __h3__ will be modified
> ```css
> h3 + p::first-line {
> 	color: red;
> }
> ```

>[!tip] After Pseudo-element
>Creates a pseudo-element that will be the __very first child__ of the selected element
>- No need to create a new element
>```css
> h2:after {
>	content: "TOP";
>	background-color: #ff370e;
>	color: #444;
>	font-size: 16px;
>	font-weight: bold;
>	display: inline-block;
>	padding: 5px 10px;
>	position: absolute;
>	top: -10px;
>	right: -25px;
> }
>```
```
```