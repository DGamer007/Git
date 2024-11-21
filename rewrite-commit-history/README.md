# Rewrite Commit History

#### Undo Commits

We can Undo Commits using **`git revert`** and **`git reset`** both. If the Commits we are trying to Undo are Public, then we should not use **`git reset`**.

#### Amend Last Commit

Sometimes it happens that we made a commit and then we realized that there is a Typo in Code. So we fix the typo and create a new Commit just for that one change. Which is not good for Commit History. So, as a solution we Amend that Typo change to the Last Commit using the following Command...

```bash
# Will Open default Code Editor with Default Commit Message (Of last commit)
git commit --amend

# With Commit Message
git commit --amend -m "Message"
```

Now, if we wanted to remove some changes from last Commit then we can use...

```bash
# This will Unstage all the changes in Last Commit
# HEAD Pointer is pointing to Second Last Commit
git reset --mixed HEAD~1

# Now, we can stage changes that are needed
# Create a new Commit
git commit -m "Message"
```

#### Amend an Earlier Commit

To Amend Earlier Commits we use `edit` option in **Interactive Rebasing**.

We mark a Commit with `edit` option and then once we are at that Commit in Rebasing, We make some changes and then we amend those changes to the Commit we have chosen to Edit. As shown below...

```bash
git commit --amend
```

#### Split Commit

If we want to split a single commit into Multiple commits then we can use **Interactive Rebasing**. We can use **`edit`** option in it. After applying edit option, Our HEAD pointer points to that commit.
Now that we want current Commit to be split, we first need to unstage all its changes and Move HEAD pointer to one step back...

```bash
# Unstage changes and go to previous Commit
git reset HEAD~1
```

After unstaging changes we can now stage appropriate changes and make commits. And these commits will replace the Commit that we accessed to _Edit_.
