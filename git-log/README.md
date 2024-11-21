# Git Log

```bash
# Commit History
git log

# Shortened Commit History
git log --oneline

# Commit History - Reverse
git log --reverse

# List the files modified in each Commit along with Commit History
git log --stat

# List all the changes made in each Commit along with Commit History
git log --patch

# List all the Commits (Even those which are ahead of the last commit)
git log --all

# Shows graph Structure of Branches and Commits
git log --graph
```

### Filtering

```bash
# Shows last 'x' commits (x is an Integer)
git log --oneline -x

# Filter by Author Name
git log --oneline --author="DGamer007"

# Filter by Date
git log --oneline --before="yyyy-mm-dd/yesterday/one week ago/two days ago"
git log --oneline --after="yyyy-mm-dd/yesterday/one week ago/two days ago"

# Filter by Commit Message
git log --oneline --grep="Message/Search term in Message"

# Filter by Content
git log --oneline -S"parser()"          # No Equal sign
```

If we want to list Range of Commits from Commit History

```bash
#                 [included] [excluded]
git log --oneline commitId1..commitId2
git log --oneline HEAD~x..HEAD~y
```

List commits between branches

```bash
# Shows commits b/w current branch and branch2
git log --oneline ..branch2

# Shows commits b/w branch1 and branch2
git log --oneline branch1..branch2
```

If we want to list commits that have modified a file (let's say file1.txt)

```bash
git log --oneline file1.txt

# Only if above command gives an Error (Mostly when we are using a filename that doesn't exist in W.T)
git log --oneline -- file1.txt
```

If we want to Format the Output of **`git log`** command...

```bash
git log --pretty=format:"Hello ! %an"

# Output
Hello ! DGamer007

# %an - Author Name
```