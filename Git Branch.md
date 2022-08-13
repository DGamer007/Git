Branching in Git provides an Isolated Environment to work and Experiment with things.

```ps1
# List all branches in Repo
git branch

# Create Branch
git branch new_branch_1

# Switch Branch
git switch new_branch_1

# Rename Branch
git branch -m new_branch_1 branch_1

# Delete Branch
# If the branch we are deleting is merged with 'main' branch then 'd' flag will be used to delete that branch.
git branch -d branch_1
# If the branch is not merged with 'main' branch then We'll use 'D' flag to Forcefully Delete that branch.
git branch -D branch_1
```