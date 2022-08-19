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
- We'll commit those changes using **`git commit`** command

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
