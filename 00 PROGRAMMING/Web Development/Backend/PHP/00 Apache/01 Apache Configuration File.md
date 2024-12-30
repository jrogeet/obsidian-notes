---
topic: php
---


Tags/Topics: #php #apache
∗:[[0 PHP|PHP]]

---
# Design

--- 
Default Apache Configuration Path:
```
usr/local/apache2/conf 
```

Default location of logs:
```
var/log/httpd
```


---
### Sections of the Default Apache Configuration File (httpd.conf)

- Where we configure the __Server Root__:
![[Pasted image 20240316215918.png]]

- Default port that Apache Listens:
![[Pasted image 20240316215957.png]]

- Modules are just Extensions of Apache:
![[Pasted image 20240316220054.png]]

- Include certain `derectives` If a __Module is Present__
![[Pasted image 20240316220222.png]]
- Here, `IfModule` __unixd_module__ exists in the configuration,
	- then `User daemon` and `Group daemon` directives will be included.




- Include other Configuration FIle using the __Include Directives__ to __SPLIT__ and __ORGANIZE__ Configuration Files
![[Pasted image 20240316220858.png]]
