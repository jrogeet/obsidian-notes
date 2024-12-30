---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info] Container
> Bundles up the applications with all of it's __dependencies__ and _configurations_
> ![[Pasted image 20240325220346.png]]
> - __Dockerfile__: Where we tell which dependencies to install to run the application.
> 	- A text file with written instruction on how to build the __Docker Image__.
> - ___Docker Image___:  Read-only executable package includes everything needed like source code, dependencies etc.
> 	- Almost the same with _Container_ but read-only
> 	- Like the `Template` of __Dockerfile__
> - _Container_: Almost the same with ___Docker Image___ but needs it to run 
> ![[Pasted image 20240326070410.png]]

