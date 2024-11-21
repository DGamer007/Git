# Git Stash

#### What is it ?

Stashing is nothing but storing our work in a safe place without including it in a Git Commit History.

```bash
# List existing Stashes in Repository
git stash list
```

Let's say I am working on **main** branch and while I am working I quickly need to fix a minor bug in **bugfix** branch. Now, if I were to _switch_ the branch I would get an error message from Git, saying that I have unsaved changes in my working tree and I need to commit them or stash them before switching the branch. Now, that I am not done working with my **main** branch changes so I dont want to commit them but I still want to keep those changes saved somewhere; Thats when Stashing comes into picture.

```bash
# Push Tracked-Unsaved changes to Stash (Won't save Untracked files/directories)
git stash -m "Stash Message"
git stash push -m "Stash Message"

# Push All-Unsaved changes to Stash (Will save Untracked files/directories)
git stash -am "Stash Message"
git stash push -am "Stash Message"
```

After Stashing the changes, Working tree will be clean and we can switch the branch.

Now, If we want to bring back those changes...

```bash
# Bring back changes without deleting Stash
git stash apply stashIndex

# Bring back changes and delete the Stash
git stash pop stashIndex
```

To see the files that are being modified in a Stash

```bash
git stash show stashIndex
```

> Options that are available on **`git show`** are available on **`git stash show`** as well.

#### Remove Stash

```bash
# Remove particular Stash
git stash drop stashIndex

# Remove all Stashes
git stash clear
```
