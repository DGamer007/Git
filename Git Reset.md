### Types of Reset

- Soft

  - HEAD Pointer will point to `<commit>`
  - Working Tree will remain untouched
  - Staging Area won't lose the changes made before RESET operation
  - Staging Area will also have changes that are made since the Commit We are trying to reset to.
    - Let's say we are on Commit `129cdsa`.
    - We want to RESET our HEAD Pointer to a Commit `7sa722s` Which is 3 Commits behind than the Above Commit.
    - We'll use `git reset --soft 7sa722s`
    - So, Our HEAD Pointer will now point to `7sa722s`
    - Staging Area will contain all the changes that are made between commits (`7sa722s`,`129cdsa`]

- Mixed

  - Default option for `git reset`
  - HEAD Pointer will point to a Different Commit
  - Working Tree won't be affected
  - Changes before RESET will be persisted but Staged Changes will be Unstaged
  - Staging area will also have changes that are made since the Commit we are trying to RESET to and they will also be Unstaged changes

- Hard

  - HEAD Pointer will point to a Different Commit
  - Staging Area will be cleared
  - Working Tree will be replaced by that Commit's Working Tree

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
