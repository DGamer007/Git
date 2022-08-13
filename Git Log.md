```ps1
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
```

### Filtering

```ps1
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

```ps1
#                 included    excluded
git log --oneline commitId1...commitId2
git log --oneline HEAD~x...HEAD~y

# CommitIds must be whole
# 3 dots syntax
```

If we want to list commits that have modified a file (let's say file1.txt)

```ps1
git log --oneline file1.txt

# Only if above command gives an Error (Mostly when we are using a filename that doesn't exist in W.T)
git log --oneline -- file1.txt
```

If we want to Format the Output of **`git log`** command...

```ps1
git log --pretty=format="Hello ! %an"

# %an - Author Name
```

> Output

```ps1
Hello ! DGamer007
```
