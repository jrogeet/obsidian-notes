---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
>[!abstract] Cookies
>A file that is stored in the user's computer
> Used for:
> - Session Management
> - Tracking Targeted Ads
> - Store Information to enhance User's Experience on the Website
> 
> __SET THE `COOKIE` BEFORE ANY OUTPUT!!!__
> ___DONT STORE `SENSITIVE DATA` TO `COOKIES`___

> [!info]
> Creating a ___Cookie___
> ```php
> setcookie(
> 	`userName`,
> 	'Gio',
> 	time() + 10,
> 	'/',
> 	'',
> 	false,
> 	false
> );
> ```
> `setcookie` __Arguments__:
> - 1st`userName`: Name of the ___Cookie___
> - 2nd`'Gio'`: Value
> - 3rd`time() + 10`: EXPIRATION
> - 4th`'/'`: Which __Directory__ the ___Cookie___ will be __VALID__
> - 5th`''`: Domain (Which domain should the ___cookie___ be available on.)
> 	- If put on the __TOP LEVEL DOMAIN__ (`mysite.com` for example) __it will be also available to all of it's__ _SUB-DOMAIN_
> - 6th`false`: Secure Parameter (Whether should the ___cookie___ be sent ONLY over __Secure parameter__ (`https` connection))
> - 7th`false`: HTTP only (If set to __True__, the ___cookie___ can ONLY be accessed by a __http protocol__)
> 	- and __CANNOT be ACCESSED__ by `Client-Side Code` like _JAVASCRIPT_
> 
> ```php
> setcookie(
> 	`userName`,
> 	'Gio',
> 	time() + (24 * 60 * 60)
> );
> ```

