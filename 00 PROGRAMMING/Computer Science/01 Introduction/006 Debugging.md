---
Course: CS50
Topic: Debugging
Week: 2
tags:
  - computerscience
  - cs50
  - c_lang
  - "#debugging"
---

> [!info] BUGS
> Mistake in a program's code.
> 
> The term '__Bug__' was popularized by Admiral Grace Hopper (worked on the `Harvard Mark I` & `II`)
> 	- First happened when she and her colleagues were documenting the processes of computing of the computers, when a __Moth__ got stuck in one of the computer's electric relay.

> [!tip] VS Code Debugger
> > - n Variables with pre-initialize value contains a __Garbage Value__ ("remnants of the computer's memory").
> ![[Pasted image 20240702184008.png]]
> 
>> [!abstract] Controls
>> - BREAKPOINT 
>> ![[Pasted image 20240702182926.png]]
>> 	This is the line where the program will _pause_
>> 
>> - ![[Pasted image 20240702183118.png]]
>> 	- Next line, right after the line of the BREAKPOINT, which is not executed yet.
>> 
>>> [!example] MAIN CONTROLS:
>>> - __Continue__ (F5)
>>> 	- ![[Pasted image 20240702184533.png]]
>>> 	- Runs the program to the end.
>>> - __Step Over__ (F10)
>>> 	- ![[Pasted image 20240702184642.png]]
>>> 	- Execute the line of code.
>>> - __Step Into__ (Alt+F11)
>>> 	- ![[Pasted image 20240702184726.png]]
>>> 	- Dive Deep into the code in that line (e.g. going inside a __Function__ used in that line)
>>> - __Step Out__ (Shift+F11)
>>> 	- ![[Pasted image 20240702184847.png]]
>>> 	- Step out of the code you `Step Into`
>>> - __Restart__ (Ctrl+Shift+F5)
>>> 	- ![[Pasted image 20240702184957.png]]
>>> 	- Restart the whole program
>>> - __Stop (Shift+F5)__
>>> 	- ![[Pasted image 20240702185029.png]]
>>> 	- Stops the program

