```ps1
# Revert to some Commit
git revert [commitId/HEAD~x]

# Revert Range of Commits
git revert [commitId1/HEAD~x]..[commitId2/HEAD~y]   #OR
git revert [commitId1/HEAD~x]...[commitId2/HEAD~y]

# Revert everything at once without Reverting Individual commit
git revert --no-commit [commitId1/HEAD~x]..[commitId2/HEAD~y]
git revert --no-commit [commitId1/HEAD~x]...[commitId2/HEAD~y]
git revert --no-commit [commitId/HEAD~x]
# This will Undo the changes made in those Commits and it will stage them so that we can create a meaningful commit.
# During this Revert Operation, we can control the whole operation with such commands
git revert --continue
git revert --abort
```
