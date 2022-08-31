Initialize Git Repository

```powershell
git init
```

Stage changes

```powershell
git add .
#OR
git add file1.txt file2.txt
#OR
git add *.txt
```

This will open Default Code Editor and in it We'll be able to Write out _Commit Message_ (Short Description) along with _Commit Description_ (Long Description)

```powershell
git commit

# Structure will be like

#1 | Commit Message
#2 |
#3 | Commit Description
```

This will stage and commit changes in a single command

```powershell
git commit -am "Message"
```
