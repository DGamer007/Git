# Git Config

#### Set Username

```bash
git config --global user.name "DGamer007"
```

#### Set Email

```bash
git config --global user.email "prajapatidhruv266@gmail.com"
```

#### Set Default Code Editor (Setting VSCode as Default Editor)

```bash
git config --global core.editor "code --wait"
```

#### Open Git Configs in Default Code Editor

```bash
git config --global -e
```

#### Set **`autocrlf`** to **`true`** for dealing with CRLF in _Windows_ and Set it to **`input`** in _Linux_ and _Mac_

```bash
git config --global core.autocrlf true

git config --global core.autocrlf input
```

#### Set Difftool

```bash
# Set DiffTool Profile
git config --global diff.tool vscode

# Set DiffTool Command to Run
git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"
```

#### Set Mergetool

```bash
# Set MergeTool Profile
git config --global merge.tool vscode

# Set MergeTool Command to Run
git config --global mergetool.vscode.cmd "code --wait --merge $REMOTE $LOCAL $BASE $MERGED"
# This config will remove a Temp file(.orig extension) after the completion of Merge Operation
git config --global mergetool.keepBackup false
```

#### Create Alias for Git Commands (Creating alias named **stat**)

```bash
git config --global alias.stat "status -s"
```

#### Configure Fast-Forward Merge

```bash
# Disable for All Git Repositories and for Every Branch
git config --global merge.ff false

# Disable for a Git Repository
git config merge.ff false

# Disable for given Branch
git config branch.[branchName].mergeoptions "--no-ff"

# Unset it
git config --global --unset merge.ff
```

#### Enable Reuse Recorded Resolution (RERERE)

Enable this feature to cache resolved conflicts so they can be automatically applied if the same conflicts arise in the future (which often happens while rebasing a series of commits).

```bash
git config --global rerere.enable true
```
