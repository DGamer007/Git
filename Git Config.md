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

Set Difftool Profile (Creating Profile for VSCode)

```powershell
git config --global diff.tool vscode
```

Set Command to run for Difftool Profile created

```powershell
git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"
```

Create Alias for Git Commands (Creating alias named **stat**)

```powershell
git config --global alias.stat "status -s"
```
