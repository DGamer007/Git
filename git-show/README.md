# Git Show

To see the Status of Single Commit

```bash
# Shows status of last commit
git show

# Shows Status of particular Commit
git show commitId
git show HEAD~x

# Shows filenames only of modified files
git show --name-only

# Shows filenames along with short status of files
git show --name-status
```

To see the final version of some file in some Commit

```bash
git show commitId:file1.txt
git show HEAD~x:file1.txt
```

In above command we access final versions of files using filenames, There is another way we can get Ids of each of those final versions of files in each commit.

```bash
# List all the files and directories modified in that Commit with unique Ids
git ls-tree commitId
git ls-tree HEAD~x

# List the content of Hierarchical Object
git ls-tree objectId
```

> In output, **Tree** represents a _Directory_ and **Blob** represents a _File_.

We can take **Blob** Id as ObjectId to see the final version of a file

```bash
# Shows content of Non-Hierarchical Object
git show objectId
```

> For ObjectId, If it is of a **Blob** then we'll see the Content of file but if it is of **Tree** then we'll get a list of files and directories in it.
