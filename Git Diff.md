`git status` command will only tell us which files have been modified but not the exact changes that have been done to those files.

Git provides us with a command using which we can compare different levels of Code

```powershell
# Compare - Working Tree and Staging Area
git diff

# Compare - Staging Area and Last Commit
git diff --staged
```

To Compare changes within range of Commits

```powershell
# Compare changes made since commitId1 to commitId2
git diff [commitId1/HEAD~x] [commitId2/HEAD~y]

# Just show filename only
git diff [commitId1/HEAD~x] [commitId2/HEAD~y] --name-only

# Shows filename along with short status
git diff [commitId1/HEAD~x] [commitId2/HEAD~y] --name-status

# We can use Dot Syntax in all of the Above commands
git diff [commitId1/HEAD~x]..[commitId2/HEAD~y]
git diff [commitId1/HEAD~x]...[commitId2/HEAD~y]
# 2 or 3 dots, both works
```

Compare branches

```ps1
# Compare current Branch with Branch2
git diff branch2

# Compare Branch1 with Branch2
git diff branch1..branch2
git diff branch1...branch2
```

To open Default Editor to compare changes

```powershell
# Compare - Working Tree and Staging Area
git difftool

# Compare - Staging Area and Last Commit
git difftool --staged
```
