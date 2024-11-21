# Git Reflog

```bash
# Shows History of HEAD Pointer in Repository
# Using this we can find lost commits if they are not garbage collected by Git
git reflog

# Shows History of 'bugfix' branch pointer
git reflog show bugfix
```

In this command 1st Column shows the CommitId of a Commit that is pointed by HEAD pointer after the Operation Shown in Last Column Completes. We can use this Logdata to determine which was the commit that is lost. And once we have found its commitId we can get it back.
