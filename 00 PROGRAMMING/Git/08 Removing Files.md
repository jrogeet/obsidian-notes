```
rm file2.txt
```

![[Pasted image 20240709202824.png]]
- `file2.txt` still exists in __Staging Area__


### List Files in __Staging Area__
```
git ls-files
```
![[Pasted image 20240709202919.png]]


## Removing file
> [!tip] Shorthand:
>  Removes in _Working Directory_ as well as the __Staging Area__
> ![[Pasted image 20240709203412.png]]


> [!note]
> To ___Remove a FILE___, you should remove it in both:
> - _Working Directory_  / Local files
> - __Staging Area__ 

- n Remove file from __STAGING AREA__ (after deleting it in your local files):
```
git add file2.txt
```
![[Pasted image 20240709203013.png | 500]]
- i COMMIT THE REMOVAL
![[Pasted image 20240709203109.png]]


> [!abstract] Remove file ONLY from __Staging Area__ BUT NOT _Working Directory_ (Local Files)
> for example we have a directory called `bin/`
> ```
> git rm --cached bin/
> ```
> if an error about `-r` showed up:
> ```
> git rm -- cached -r bin/
> ```
> then commit
> ![[Pasted image 20240709205416.png]]



