```ps1
# Clone Remote Repo
git clone [repo_url]
# Change root directory name
git clone [repo_url] [dirname]
# Clone a specific branch
git clone -b [branch] [remote_repo] [dirname]

# Download Commits from Remote Repo
git fetch [remote] [branch]

# Download + Merge Commits from Remote Repo into Local branch
# Will create a Merge Commit
git pull [remote] [branch]

# Will use Rebase & Merge approach
git pull --rebase [remote] [branch]

# Push/Upload Commits to Remote Repo
git push [remote] [branch]
# Push Commits Forcefully - Will Rewrite the Commit History on Remote Repo as well (Try not to use this)
git push -f [remote] [branch]

# Push Tags to Remote Repo (By default Tags won't be pushed to Remote Repo)
git push [remote] [tag]
# To remove Tag
git push [remote] --delete [tag]
```
