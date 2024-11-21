# Git Restore

#### Unstage changes

```bash
git restore --staged file1.txt
git restore --staged file2.txt file3.txt
git restore --staged .
```

> If the file had been added then restoring it from Staging Area would mark it as Untracked.

#### Discard Changes

```bash
git restore file1.txt
git restore file2.txt file3.txt
git restore .
```

> If the file is Untracked then after restoring, it would remain Untracked.

#### Remove Untracked changes

```bash
# Clean all Untracked files and Directories in Working Tree
git clean -fd

# Clean specific Untracked file(s) in Working Tree
git clean -f file1.txt
git clean -f file2.txt file3.txt
git clean -f *.txt

# Clean an entire Untracked Directory in Working Tree
git clean -fd tests

# f - force
# d - directory
```
>

The restore methods mentioned above will use last commit as a Source for Restoring, But if we want to restore files from some other commit then...

```bash
git restore --source=(commitId/HEAD~x/branch) file1.txt
git restore --source=(commitId/HEAD~x/branch) file2.txt file3.txt
git restore --source=(commitId/HEAD~x/branch) .
```
