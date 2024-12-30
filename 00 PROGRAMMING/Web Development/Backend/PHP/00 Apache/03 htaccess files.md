---
topic: php
---


Tags/Topics: #php #apache
∗:[[0 PHP|PHP]]

---
# Design

--- 
Distributed Configuration Files

>[!info] htaccess
> - Distributed Configuration Files
> - Applies Configuration changes where `htaccess file` is located or to its __Directory__ ___and it's Sub-directory___.
> - Changes are __Effective Immediately__. (No need to restart Apache Server)
> - __Not all directives__ can be placed in `htaccess files`
> 	- __MAIN CONFIGURATION__ controls what directives can be put in `htaccess files`
> - __DO NOT USE `htaccess files` UNLESS NEEDED TO__
> 
>> [!tip] Use-cases
>> You don't always have __root access to the server__ and to the __Main Configuration File__
>> - Re-write URLs
>
>
>> [!abstract] Have access to __Main Configuration File__
>> RECOMMENDED: __Disable `htaccess` entirely__: `AllowOverrided None`
>> - Re-write rules to the Main Conf. File
>> - Put it in ___Separate Configuration File___ and Include in the __Main__
>> - Add directives to _Virtual Host Section_

---


### URL Re-writing Basic Example:
```
<IfModule mod_rewrite.c>
	RewriteEngine On
	
	RewriteCond %{REQUEST_FILENAME} !-d
	RewriteCond %{REQUEST_FILENAME} !-f

	RewriteRule ^ index.php [L]

</IfModule>
```

- `RewriteCond %{REQUEST_FILENAME} !-d`
	`RewriteCond %{REQUEST_FILENAME} !-f`
	- __Conditions__ to make sure the `Requested File Name` is ___NOT___ an __ACTUAL FILE__ or __DIRECTORY__