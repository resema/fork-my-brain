#git #cheat 

see also [[cherry picking in git]]

By using `git log` to find the ID of the commit you want pick. Then checkout the feature branch, assuming your changes have been committed, and run `cherry-pick`.

```sh
git log # -> get commit ID
git switch <branch_name> # -> alternatively `git checkout <branch_name>`
git cherry-pick <commit_sha> # -> pick commit
```