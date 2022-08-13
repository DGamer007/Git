To get an Author of each line in a file

```ps1
# Shows full content of file1.txt
git blame file1.txt     # Shows Author Username
git blame -e file1.txt  # Shows Author Email

# Shows first 3 lines of file with Author
git blame -L 1,3 file1.txt
```
