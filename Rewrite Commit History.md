### Undo Commits

We can Undo Commits using **`git revert`** and **`git reset`** both. If the Commits we are trying to Undo are Public, then we should not use **`git reset`**.

### Amend Last Commit

Sometimes it happens that we made a commit and then we realized that there is a Typo in Code. So we fix the typo and create a new Commit just for that one change. Which is not good for Commit History. So, as a solution we Amend that Typo change to the Last Commit using the following Command...

```ps1
# Will Open default Code Editor with Default Commit Message (Of last commit)
git commit --amend

# With Commit Message
git commit --amend -m "Message"
```

Now, if we wanted to remove some changes from last Commit then we can use...

```ps1
# This will Unstage all the changes in Last Commit
# HEAD Pointer is pointing to Second Last Commit
git reset --mixed HEAD~1

# Now, we can stage changes that are needed
# Create a new Commit
git commit -m "Message"
```
