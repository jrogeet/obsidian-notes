>[!CHECK]- What can in-browser JavaScript do?
> - Add new HTML to the page
> 	- change the existing content
> 	- modify styles
> - React to user actions
> 	- run on mouse clicks
> 	- pointer movements
> 	- key presses
> - Send requests over the network to remote servers
> 	- download and upload files (AJAX and COMET technologies)
> - Get and set cookies
> 	- ask questions to the visitor
> 	- show messages
> - Remember the data on the client-side (local storage)

>[!DANGER]- What CAN'T in-browser JavaScript do?
>- JavaScript on a webpage can't read/write arbitrary files on the hard disk
>	- Can't copy or execute programs
>	- No direct access to OS functions
> - Different tabs/Windows generally do not know about each other.
> - Can easily communicate over the net to the server where the current page came from.
> 	- BUT, it's ability to receive data from other sites/domain is crippled.

## \<script>
Simple scripts : inside HTML
Complex scripts : separate files

### Script tag Attributes
- ___Type___ attribute - \<script __type=...__>
	- old HTML(HTML4) requires scripts to have a __type__ -- ___type = "text/javascript"___
	- It's not required anymore

- ___Language___ attribute - \<script __language=...__>
	- was meant to show the language of the script
	- no longer make sense since JavaScript is the default language
	- no need to use
### External Scripts
Separate script files use ___src___ attribute

Absolute path:
- Specific location
```javascript
<script src="/path/to/script.js"></script>
```
Relative path:
- Same folder
```javascript
<script src="script.js"></script>

// OR

<script src="./script.js"></script>
```

```javascript
console.log("fuck you")
```

URL:
```javascript
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.11/lodash.js"></script>
```

Multiple scripts:
- Use multiple script tags
```javascript
<script src="/js/script1.js"></script>
<script src="/js/script2.js"></script>
```


>[!caution] if ___src___ is set, Script Content is Ignored
> Single \<script> tag can't have both ___src___ and __code__ inside
> ```javascript
> <script src ="file.js">
 	alert(1); // the content is ignored, because src is set
 </script>
> ```







