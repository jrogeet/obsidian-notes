---
Topic: Git
---
> [!abstract] Master Branch / Main
> ![[Pasted image 20240720204721.png]]
> - __Master Branch__: The stable version of the codebase
> - Feature Branch: Copies the current state of the Master Branch and where you'd modify like adding features into the application/codebase _WITHOUT AFFECTING_ THE Master Branch.
> - Merge Commit: Once the modification is successful, we can merge it to the Master Branch


#### Create Branch
```
git branch branch-name
```
##### Check which branch you're currently on:
```
git branch -a
```
![[Pasted image 20240720212221.png]]
- The one with asterisk (`*`) is the __Current Branch__

#### Switch current branch
```
git checkout branch-name
```
#### Delete Branch
Merged Branch:
```
git branch -d branch-name
```

Not Merged:
```
git branch -D branch-name
```

### Merging Branches
- n You should be in the __Master Branch__ when merging a branch into it.
```
git merge branch-name
```

#### Merge Conflicts:
https://youtu.be/XX-Kct0PfFc?t=228


