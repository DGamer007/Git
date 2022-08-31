# Git Branch

Branching in Git provides an Isolated Environment to work and Experiment with things.

```ps1
# List all branches in Repo
git branch

# Shows branches that are merged with current Branch
git branch --merged

# Shows branches that are not merged with current Branch
git branch --no-merged

# Create Branch
git branch new_branch_1

# Switch Branch
git switch new_branch_1

# Create a Branch and then Switch to it
git switch -c new_branch_2

# Create a Branch, Set Upstream to it then Switch to it
git switch -c new_branch_3 remote/new_branch_3
# new_branch_3 -> Local Branch
# remote/new_branch_3 -> Remote Branch named 'new_branch_3' on 'remote'

# Rename Branch
git branch -m new_branch_1 branch_1

# Delete Branch
# If the branch we are deleting is merged with 'main' branch then 'd' flag will be used to delete that branch.
git branch -d branch_1
# If the branch is not merged with 'main' branch then We'll use 'D' flag to Forcefully Delete that branch.
git branch -D branch_1

# Shows how remote and local branches are diverging
git branch -vv

# Shows Remote Tracking Branches
git branch -r

# Set Upstream to Current Branch
git branch -u github/main

# Unset Upstream from Current Branch
git branch --unset-upstream
```
