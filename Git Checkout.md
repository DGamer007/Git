# Git Checkout

Checking out any commit will replace our code in Working Tree with the Code of the Commit we are checking out.

Checkout any Commit

```ps1
git checkout commitId
git checkout HEAD~x
```

If we want to restore Deleted files from previous commits

```ps1
git checkout commitId file1.txt
git checkout HEAD~x file1.txt
```

When we are restoring any deleted file from previous commits, we should make sure that the file we are trying to restore exists in the commit we're trying to restore it from and We typically find those kind of Commits using

```ps1
git log --oneline -- filename
```

> We cannot Switch to another Commit If we have Uncommited Changes in Staging Area
