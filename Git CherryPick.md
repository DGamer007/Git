Let's say we have a branch **`feature`** and one of its commits has something valuable that we want to take in branch **`main`**. So, we can Pick that Commit of **`feature`** branch and merge it into branch **`main`** as shown below...

```ps1
# Switch to Branch - Main
git switch main

# Pick and Merge that Commit (Will Stage changes)
git cherry-pick commitId/HEAD~x

# Create a Commit (Without explicit Message it will take the message of Picked Commit)
git commit
```
