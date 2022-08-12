Remove files from Directory (Typical Unix Command)

```powershell
rm file1.txt
rm file2.txt file3.txt
rm *.txt
# For Directory
rm -r src
```

List files in Git Staging Area

```powershell
git ls-files
```

Now, whenever we want to remove a file which is being tracked by Git, We need to Remove it from both **Working Tree** and **Staging Area**. So, if we were to do it manually (let's say with **rm** command) then we'll have to first remove it from **Working Tree** and then manually remove it from **Staging Area** by Staging the change _(Deleted)_ using **`git add`** command.

Git Provides us with a command that can do those both things

```powershell
git rm file1.txt
git rm file2.txt file3.txt
git rm *.txt
git rm -r src
```
