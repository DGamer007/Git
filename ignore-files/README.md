# Ignore Files

If we don't want Git to track a file or an entire directory from our Working Tree then we mention that _filename_ or _directory name_ in **.gitignore** file

So, let's say We have created a file named _file1.txt_ and we don't want Git to track it, then we'll mention it in **.gitignore** file as...

`.gitignore` 👇

```
# Single file
file1.txt

# Filepath
src/file1.txt

# Directory
src/
```

Now, let's say We created a file that we didn't want Git to track but Accidently we Commited that file once. Now, That file is also in **Working Tree** and in **Git Staging Area**. So, first we need to remove that file from _Git Staging Area_ and then mention that file in **.gitignore** file to stop Git from tracking it afterwards.

If we wanted to remove that file completely then we could use `git rm` command, which will remove it from Git Staging Area as well as Working Tree. But We want to keep that file in Working Tree and just remove it from Git Staging Area. So, to remove a file **just from Staging Area**...

```bash
git rm --cached file1.txt
```
