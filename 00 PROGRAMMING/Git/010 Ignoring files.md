> [!example] `.gitignore` Templates
> https://github.com/github/gitignore



Some files like log files, binary files that was generated from compiling files etc.

- i Ignores _Files_ and __Directories__ listed in `.gitignore`
```
.gitignore
```

```
echo logs/ > .gitignore
```
![[Pasted image 20240709204440.png]]
- For example, here the __Directory__ `logs/` and its files are ignored
- `*.log` refers to all `.log` files

### Commiting the `.gitignore`
![[Pasted image 20240709204537.png]]
![[Pasted image 20240709204555.png | 500]]


> [!caution] Ignore files already uploaded to repository
> GIT will __NOT IGNORE__ files that already in repository when added after to the `.gitignore`





