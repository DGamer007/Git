# Git Tag

Show all available Tags in Repository

```ps1
# Shows list of tags
git tag

# Shows list of tags with tag Messages
git tag -n
```

### Tag a Commit

This is a Lightweight Tag which won't contain any additional Information

```ps1
# Tag last Commit
git tag v1.0

# Tag particular Commit
git tag v1.1 commitId
git tag v1.2 HEAD~x

# Remove tag
git tag -d v1.1
```

### Annotated Tag

This type of Tag has additional information such as DateTime of tag creation, Tagger name, Message

```ps1
# Tag last Commit
git tag -a v1.0 -m "Message"

# Tag particular Commit
git tag -a v1.1 -m "Message" commitId
git tag -a v1.2 -m "Message" HEAD~x

# a - Annotation for Tag
# m - Message for Tag
```

> We can use Tag as a Pointer for `git show`, `git restore`, `git checkout`...
