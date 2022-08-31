### Types of Merge in Git

- Fast-Forward Merge (If branches are not Diverged)
- 3-way Merge (If branches are Diverged)

If we want to merge **branch2** into **branch1**

```ps1
# First Switch to the branch you want to merge INTO
git switch branch1
git merge branch2

# Merge with No-Fast-Forward Option
git merge --no-ff branch2
```

### When we have Merge Conflicts

- If there is a Merge Conflict, We'll be shown a CONFLICT message by Git.
- Git tries to merge files automatically if the changes are not overlapping.
- Now, for the changes that cannot be merged automatically; We do those manually.
- We'll open text editor of our choice.
- We'll Accept the changes either **Current**, **Incoming** or **Both**.
- Do not Introduce any extra code while we are solving Conflicts in a Merge Operation.
- When we are done accepting those changes we'll stage those files using **`git add`** command
- We'll commit those changes using **`git commit`**

> While merge Operation, we usually don't provide a _Commit Message_ with `git commit` command because if we don't provide a Commit Message, Git will open a default text editor for a Commit Message with a predefined Merge Commit Message to commit the Merge.

```ps1
# To Abort Merge Operation
git merge --abort
```

### Undo Faulty Merge Commit

If we haven't shared our code with anyone else then we can use `git reset` and delete the Current Faulty Merge Commit and Create a new Correct Merge Commit from old bases.

```ps1
# Reset to the tip of Merge Commit
git reset --hard commitId/HEAD~x
```

If we have shared our code with someone then we would not like to rewrite the Commit History in a complicated way. So here we'll use `git revert` to create a new Merge Commit which will resolve Faulty Merge Commit's code.

```ps1
# Revert to i-th parent of Merge Commit
git revert -m parentIndex commitId/HEAD~x
```

> If we merged **feature** branch INTO **main** branch then 1st Parent of the Merge Commit will be the **main** branch.

### Squash & Merge

Let's say we are working on **`bugfix`** branch and after resolving the Bug, its time to merge that branch into **`main`** branch. Now, we want to merge those branches but We also don't wanna keep commits of **`bugfix`** branch in our History. So, We can create a commit that Combines all the changes made throughout **`bugfix`** branch and then just attach that Commit to **`main`** branch.

Combining those multiple commits into a Single Commit is Called Squashing.

```ps1
# Switch to branch1
git switch branch1
# Squash Changes
git merge --squash branch2
```

These Squashed changes will be staged and we'll have to create a Commit Manually.

After performing **Squash & Merge**, we still won't be able to see it in Merged Branches list...

```ps1
git branch --merged
```

So, It is highly suggested that we Delete Squash & Merge branches Just after we make a Successful Merge.

### Rebase & Merge

Suppose We have 3 commits on branch **`feature`** and after that we made a commit on Branch **`main`**. Now, If we want to perform **Fast-Forward** merge only between these 2 branches then Right now it seems impossible, because branch **`main`** already has another commit; So the branches are already diverged. Unless if we Change the base of branch **`feature`** to the Tip of branch **`main`**. To do that we can perform a Rebase Operation on Branch **`feature`** which will change the Base of branch **`feature`** and then we can apply Fast-Forward Merge to it.

```ps1
# Switch to Branch - Feature
git switch feature

# Perform Rebase operation on feature to change the Base to the tip of branch main
git rebase main
# Resolve conflicts if any

# Switch back to Branch - Main
git switch main

# Perform Fast-Forward Merge
git merge feature  # OR
git merge --ff-only feature
```

> During the Rebase Operation...

```ps1
# Abort Rebase Operation
git rebase --abort

# Accept current Commit and Continue Rebase Operation
git rebase --continue

# Skip current Commit and Continue Rebase Operation
git rebase --skip
```
