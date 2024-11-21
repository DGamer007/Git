# Git Rebase

Git Rebase serves the purpose of Integrating Changes from One Branch onto Another.

It kind of Changes the Base of Branch.

Mostly used to keep the Commit History Linear.

```bash
# Switch to bugfix Branch
git switch bugfix

# Move the base of 'bugfix' Branch to the Tip of 'main' Branch
git rebase main
```

#### Interactive Rebasing

Start Interactive Rebasing

```bash
# Starts Rabasing from the Provided Commit to Last Commit
git rebase -i [parentCommit/HEAD~x]

# Here Caret sign denotes Parent of CommitId/HEAD~y
git rebase -i [commitId/HEAD~y]^


# Control commands for Rebasing Operation
git rebase --continue
git rebase --skip
git rebase --abort
```

#### Options in Interactive Rebasing

- edit

Using this Option we can Edit the Chosen Commit. And Edit means that we can add some changes or can remove something from that Commit and Amend those changes to that commit using `git commit --amend`.

- drop

This option helps us to Drop/Delete Commits. Droping Commits might cause some conflicts so we have to deal with them.

- squash

Using this option we can combine changes into Parent Commit. In Squashing We'll be asked to set a Commit Message at last.

- fixup

Works same as Squash but at the end it doesn't ask us for a Commit Message. It'll take the Commit Message of Parent Commit.

> In Squash or Fixup If we want some commits to be squashed but they are not sequential then we can rearrange them in order and then we can Squash or Fixup them.
