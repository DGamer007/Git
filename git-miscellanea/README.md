# Git Miscellanea: Tools and Techniques

- In VSCode, the **Timeline** tab in the sidebar shows all commits that have modified the currently focused file.

- Before setting up a remote tracking or upstream branch, it's a good practice to run `git fetch` first. This ensures that your local repository is synced with the remote branches and prevents potential errors if the branch hasn’t been fetched locally yet. Once the upstream branch is configured, you can push, pull, or fetch commits without needing to specify the remote and branch names.
