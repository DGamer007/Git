# Rename or Remove files

Move or Rename File (Unix Command)

```powershell
# Renaming
mv file1.txt file2.txt

# Moving
mv file1.txt src/file1.txt
```

Renaming and Moving a File will make 2 changes...(Let's say in above case)

- **Deleting** _file1.txt_
- **Creating** _file2.txt_ OR _src/file1.txt_

Now, If we were to Rename or Move a File which is being tracked by Git, Then we'll have to stage both of the changes mentioned above.

Git provides us with a command that can do both, Renaming or Moving and Staging necessary changes.

```powershell
# Renameing
git mv file1.txt file2.txt

# Moving
git mv file1.txt src/file2.txt
```
