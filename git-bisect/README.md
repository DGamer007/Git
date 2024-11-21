# Git Bisect

#### Why ?

Let's say there is a Bug in our Code and we want to find out which commit introduced this Bug

So, the typical Approach would be...

- We checkout every commit using **`git checkout`**
- Run Automated and Manual Tests on every one of them
- Conclude whether the currently checked out commit is **The Buggy Commit** or not
- Repeat untill we find the Buggy commit

This is a Linear Approach which is LAME.

Git Provides us with a Tool called **Bisect** which can help us find the Buggy commit efficiently

It uses Binary Search Technique to checkout commits.

#### Process of Bisecting

- Initialize Bisect Process

```bash
git bisect start
```

- Give it a Bad Commit

```bash
# Mark some Commit as Bad Commit
git bisect bad commitId
git bisect bad HEAD~x

# Mark current Commit as Bad Commit
git bisect bad
```

- Give it a Good Commit

```bash
# Mark some Commit as Good Commit
git bisect good commitId
git bisect good HEAD~x

# Mark current Commit as Good Commit
git bisect good
```

- Now, Git will checkout the Commit which is in the middle of Bad and Good Commit, and we'll have to tell it whether the checkedout commit is Bad or Good.

```bash
# Mark it as a Good Commit
git bisect good

# Mark it as a Bad Commit
git bisect bad
```

- After repeating above step for a while, We'll finally react at the Buggy Commit and Git will show full Status of that Buggy commit.

- Once we've found out which Commit Caused the bug, we can now switch back to where we started the Bisecting Process using...

```bash
git bisect reset
```
