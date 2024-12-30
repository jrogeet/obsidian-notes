---
topic: javascript
---
Tags/Topics: #javascript #codequality
∗:[[01 Javascript|JavaScript]] 

---
# Debugging

--- 

## Breakpoints

>[!INFO] Breakpoint
> - A __breakpoint__ is a point of code where the debugger will automatically pause the JavaScript execution.
> 
> While the code is paused, we can examine current variables, execute commands in the console etc. In other words, we can debug it.
> 
> We can always find a list of breakpoints in the right panel. That’s useful when we have many breakpoints in various files. It allows us to:
> - Quickly jump to the breakpoint in the code (by clicking on it in the right panel).
> - Temporarily disable the breakpoint by unchecking it.
> - Remove the breakpoint by right-clicking and selecting Remove.
> - …And so on.


![[Pasted image 20240108201502.png]]
Click at the line number, before the codes.
In this example,  we clicked two numbers `4` and `8`.
That's how you set a `breakpoint`.

## The "debugger" command

```javascript
function hello(name) {
	let phrase = `Hello, ${name}!`;
	
	debugger; // <-- the debugger stops here
	
	say(phrase);
}
```

Such commands __works only when `development tools` are open__, otherwise the browser ignores it.

## Pause and look around
Some things are loaded during page load, so reload the page to activate the `breakpoints` you've set.

>[!example]
>>[!info] Watch
>> __shows current values for any expressions.__
>> - Click the `+` and input an _expression_.
>> - The debugger will show its value
>> - Automatically recalculating it in the process of execution.
>
>
>>[!danger] Call Stack
>>__shows the nested calls chain.__
>> At the current moment the debugger is inside `hello()` call, called by a script in `index.html` (no function there, so it's called "anonymous").
>> 
>> If you click on a stack item (e.g. "anonymous"), the debugger jumps to the corresponding code, and all its variables can be examined as well.
>
>
>> [!caution] Scope
>> __current variables__
>> - `Local` shows local function variables.
>> 	- See their values highlighted right over the source.
>> - `Global` has global variables (out of any functions).


## Tracing the execution

>[!example] Trace the script
> - "__Resume__": _continue execution_, hotkey `F8`
> 	 ![[Pasted image 20240108221747.png]]
> 	- Resumes the execution. If there are no additional breakpoints, then the execution just continues and the debugger loses control.
> - "__Step__": _run the next command_, hotkey `F9`
> 	![[Pasted image 20240108222000.png]]
> 	- Clicking this will step through all script statements one by one.
>  - "__Step over__": _run the next command, but don't go into a function_, hotkey `F10`
> 	 ![[Pasted image 20240108222132.png]]
> 	 - like "__Step__" but behaves differently if next statement is a _function call_ (not __built-in__ like `alert`)
> - "__Step into__", hotkey `F11`
> 	![[Pasted image 20240108222505.png]]
> 	 - similar to "__Step__", but behaves differently in case of `asynchronous function calls`
> 		 - "__Step__" command ignores actions, such as `setTimeout`(scheduled function call) that execute later.
> 		- "__Step into__" goes into their code, waiting for them if necessary.
> - "__Step out__": _continue the execution till the end of the current function_, hotkey `Shift+F11`
> 	![[Pasted image 20240108222944.png]]
> 	- Continue  execution and stop at the very last line of current function.
> 		- useful when accidentally entered a nested call using "__Step__"--continue to its end as soon as possible.
> - __enable/disable all breakpoints.__
> ![[Pasted image 20240108223231.png]]
> 	- Mass on/off for breakpoints.
> - __enable/disable automatic pause in case of an error__.
> 	![[Pasted image 20240108223510.png]]
> 	- When enabled, when dev tools is open, _an error during the script execution automatically pauses it._




