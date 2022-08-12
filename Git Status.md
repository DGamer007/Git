Get Status of Git Repository

```powershell
# Verbose Output
git status

# Short Output
git status -s
```

Shorten Output form:

```powershell
MM file1.txt    # Modifications in S.A and W.T
?? file2.txt    # Untracked Changes
M  file3.txt    # Modifications in S.A
 M file4.txt    # Modifications in W.T
A  file5.txt    # Added file to S.A
AM file6.txt    # Added file to S.A and Modifications in W.T
```

Basically First Column represents **Staging Area**, Second Column represents **Working Tree** and Third Column represents **Filename**

```
# Legends

M - Modified
? - Untracked
A - Added
S.A - Staging Area
W.T - Working Tree
```
