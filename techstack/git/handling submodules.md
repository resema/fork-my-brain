#git #cheat #submodule

#### Initialize
-   `git submodule update --init --recursive`

#### [](/https://github.com/resema/cheatsheets/blob/main/git.md#update-)Update
1.  `cd repo/submodule`
2.  `git fetch`
3.  `git log --online origin/main`
4.  `git checkout -q <HASh>`

Or

```sh
get pull origin main

git add .
git commit -m 'blub'
git push
```

Or

`git submodule update --remote --merge`