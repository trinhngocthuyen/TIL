## Recover lost commits

### What are considered lost commit?
- You incidentally clear stash: `git stash clear`
- You reset to a commit (all commits between the current commit and the new one are lost): git reset abc12345 (In this case, I prefer tracing reflogs rather than this solution)

If you run into this case, don't panic b/c you probably recover what you deleted:
```
git fsck --lost-found
```

You may see:
```
dangling commit 530e7b19980ff58689f80b59e29600d5f46c5365
dangling blob e69de29bb2d1d6434b8b29ae775ad8c2e48c5391
dangling commit e38b12f18c22c6ac4f3d62f37c29554c417bb7a4
dangling commit a8b2da68402f89ce12deabd02832369e042028e2
dangling commit 3176af242bc9eefc295aaa5eb2d1c291278fb20d
```

For now, just care about dangling commit: 
```
git fsck --lost-found | grep "dangling commit"
```

Then, try checking out those dangling commits and verify if it succeed. Usually, the latest action is on the top
