`git status` command will only tell us which files have been modified but not the exact changes that have been done to those files.

Git provides us with a command using which we can compare different levels of Code

```powershell
# Compare - Working Tree and Staging Area
git diff

# Compare - Staging Area and Last Commit
git diff --staged   #OR
git diff --cached
```

To compare changes between two Commits or Branches

```powershell
# Compare changes between commitId1/branch1 and commitId2/branch2
git diff [commitId1/HEAD~x/branch1] [commitId2/HEAD~y/branch2]

# Just show filename only
git diff [commitId1/HEAD~x/branch1] [commitId2/HEAD~y/branch2] --name-only

# Shows filename along with short status
git diff [commitId1/HEAD~x/branch1] [commitId2/HEAD~y/branch2] --name-status

# Shows Diff for only the Filename Provided
git diff [commitId1/HEAD~x/branch1] [commitId2/HEAD~y/branch2] [filename]

# Shows Diff between current Branch/Commit and Provided Branch/Commit
git diff [commitId/HEAD~x/branch]

# We can use Dot Syntax in all of the Above commands
git diff [commitId1/HEAD~x/branch1]..[commitId2/HEAD~y/branch2]
```

To use Default Editor for Operations mentioned above

```powershell
# use 'difftool' instead of 'diff'
git difftool
```
