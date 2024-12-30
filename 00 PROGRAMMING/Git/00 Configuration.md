---
Topic: Git
tags:
  - "#configuration"
---
![[Pasted image 20240709151534.png | 300]]


### Levels of Configuration
![[Pasted image 20240709151643.png | 600]]

- ___SYSTEM___ - All Users of the Computer
- __GLOBAL__ - All repositories of the current user 
- _LOCAL_ - The current repository/folder

---

### Step-by-Step:
Preferably use ___GIT BASH___ instead of windows command prompt
```git
git config --global user.name "John Rogee Turqueza"
```
- Double Quotes `" "` because there's __space__

```git
git config --global user.email 'jo********21@gmail.com'
```
- Single Quote `' '` because there's __no space__

Type in `code` in the terminal (__Git)
```git
code
```
- VS Code or your DEFAULT text editor/ide should pop-up

```git
git config --global core.editor "code --wait"
```
- Wait for VS Code to close

```git
git config --global -e
```
- opens the `.gitconfig` file in VS Code
![[Pasted image 20240709152519.png]]

> [!question] __END OF LINES__ 
> ![[Pasted image 20240709152710.png]]
> ![[Pasted image 20240709152825.png]]
> 
> - Windows:
> ```git
> git config --global core.autocrlf true
> ```
> 
> - MAC
> ```git
> git config --global core.autocrlf input
> ```


## Git Help
```git
git config --help
// OR
git config -h
```


