## Misc

##### Clone git with submodules
```
git clone --recursive URL
```

##### Export diff between 2 commits of specific folders
```
git diff commit1 commit2 -- folder1 -- folder2
```

##### View file changed between 2 commits
```
git diff --name-only commit1 commit2
```

##### Apply diff from a file
```
git apply change.diff
```
