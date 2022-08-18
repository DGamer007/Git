Set Username

```powershell
git config --global user.name "DGamer007"
```

Set Email

```powershell
git config --global user.email "prajapatidhruv266@gmail.com"
```

Set Default Code Editor (Setting VSCode as Default Editor)

```powershell
git config --global core.editor "code --wait"
```

Open Git Configs in Default Code Editor

```powershell
git config --global -e
```

Set **`autocrlf`** to **`true`** for dealing with CRLF in _Windows_ and Set it to **`input`** in _Linux_ and _Mac_

```powershell
git config --global core.autocrlf true

git config --global core.autocrlf input
```

Set Difftool

```ps1
# Set DiffTool Profile
git config --global diff.tool vscode

# Set DiffTool Command to Run
git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"
```

Set Mergetool

```ps1
# Set MergeTool Profile
git config --global merge.tool vscode

# Set MergeTool Command to Run
git config --global mergetool.vscode.cmd "code --wait --merge $REMOTE $LOCAL $BASE $MERGED"
# This config will remove a Temp file(.orig extension) after the completion of Merge Operation
git config --global mergetool.keepBackup false
```

Create Alias for Git Commands (Creating alias named **stat**)

```powershell
git config --global alias.stat "status -s"
```

Disable Fast-Forward Merge

```ps1
# Disable for All Git Repositories
git config --global ff no

# Disable for a Git Repository
git config ff no
```
