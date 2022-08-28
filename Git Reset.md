### Types of Reset

- Soft (Removes the commit Only)

  - HEAD Pointer will move
  - Working Tree and Staging Area will remain untouched.

- Mixed (Unstage files)

  - Default option for `git reset`
  - HEAD Pointer will move
  - Working Tree won't be affected
  - Staging Area will hold only THE COMMIT, Other changes will be unstaged

- Hard (Discard Local Changes)

  - HEAD Pointer will move
  - Staging Area and Working Tree will hold only THE COMMIT

Reset HEAD Pointer to a Commit

```ps1
# Mixed Mode
git reset commitId
git reset HEAD~x

# Soft Mode
git reset --soft commitId/HEAD~x

# Hard Mode
git reset --hard commitId/HEAD~x

# Reset just a File
git reset commitId/HEAD~x filename
git reset commitId/HEAD~x -- filename
```

#### Soft Mode usecase

> Resetting with a Soft Mode is kind of a solution for Squashing Commits. So, as we know We can Just Reset the Location of HEAD Pointer with Soft Mode, which will keep Changes in place and also give us changes in Staging Area that have been made since the Commit We have reset to. So, Now that all those changes we have in Staging Area; We can just create a new commit Which will be the Squashed Commit. And the actual Commits will be Garbage collected by Git.
