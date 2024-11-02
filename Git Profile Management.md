# Git Profile Management

When starting out with Git, you typically use a single profile—usually your personal profile. However, once you begin working professionally, you’ll likely need to manage both a work and a personal Git profile on the same machine. It’s essential to ensure that commits intended for work repositories aren’t associated with your personal Git profile and vice versa.

## Key Considerations for Managing Profiles

1. #### Setting Up Local Git Profiles

   Each Git profile records your identity on commits, attaching your username and email as metadata to each commit. For effective profile management, make sure:

   - Work-related commits use your work profile metadata.
   - Personal projects use your personal profile metadata.

   Additionally, if you’re working as a freelancer or in varied roles, you may need to set up multiple profiles to cater to different use cases.

   In summary, ensure that specific use cases are considered, and their configurations are tailored appropriately. This will help you maintain distinct profile metadata for each scenario, streamlining your workflow and avoiding any potential confusion in your commits.

2. #### Accessing Repositories

   Managing profiles goes beyond setting usernames and emails; it also involves configuring access to different repositories. Typically, you'll access repositories using SSH keys. However, managing multiple SSH keys on a single machine can be complex.

   - **Separate SSH Keys:** Configure distinct SSH keys for work and personal use to avoid access conflicts and keep profiles organized.

   - **SSH Configurations:** Use an SSH configuration file to handle multiple keys, ensuring each profile accesses only the intended repositories.

3. #### Maintaining Signing Keys

   In addition to SSH keys, signing keys help verify your identity on each commit, adding a layer of security and authenticity. With signed commits, collaborators and stakeholders can trust that the commits come from you.

   - **Separate Signing Keys:** Use different signing keys for work and personal commits to ensure a clear distinction between profiles. This practice helps prevent accidental cross-association between work and personal repositories.

   - **Signing Configuration:** Configure each profile to use its specific signing key by adjusting your global and local Git settings.

   <details>
   <summary><strong>Learn more about Commit Signing</strong></summary>

   - What is Commit Signing in Git? – [freeCodeCamp](https://www.freecodecamp.org/news/what-is-commit-signing-in-git/)
   - Why You Should Sign Your Commits on GitHub? [Medium](https://medium.com/@harutyunabgaryann/why-you-should-sign-your-commits-on-github-2ebd2d4102ee)
   - Commit Signature Verification – [GitHub Docs](https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification)
   - The How and Why of Signing Commits – [WithBlue](https://withblue.ink/2020/05/17/how-and-why-to-sign-git-commits.html)

   </details>

## Configuring and Maintaining Key Aspects

### 1. Setting Up Local Git Profiles

Before managing local profiles, it’s essential to set a global Git profile based on the type of device you’re using. This global setup ensures that any repositories not explicitly configured will use the specified profile information.

#### Set Global Profile:

- **Work Device:** Configure the global user profile for work repositories.
- **Personal Device:** Configure the global user profile for personal repositories.

  Use the following commands to set the global profile:

  ```ps1
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```

This global setup will serve as a fallback for any repositories not explicitly configured.

Once the global profile is established, you can proceed with either of the methods below for managing local Git profiles:

#### Method 1: Configuring Profiles Per Repository

1. **Organize Repositories by Type:** Maintain separate directories for work and personal projects to keep track of where each profile should apply.

2. **Configure Local Profile Settings:** For each repository, specify the user profile information using local Git configuration. This ensures that commits made in each repository reflect the correct profile.

   ```ps1
   git config --local user.name "Your Work Name"
   git config --local user.email "yourwork@example.com"
   ```

3. **Update Profile for New Repositories:** When you add a new repository, configure the appropriate profile information using `--local` option. While this approach requires you to set up the profile for each repository individually, it helps maintain organization and ensures that your commit metadata is precise and relevant for each specific project.

#### Method 2: Conditional Configuration Using Directory-Based Profiles

1. **Create Category-Specific Directories:** Set up separate directories for each profile category (e.g., Personal, Work, Freelance). For each directory, create a dedicated `.gitconfig` file to store specific profile details.

2. **Configure Category-Specific `.gitconfig` Files:** Inside each category directory, create a `.gitconfig` file with the profile information.

   ```ps1
   # Example .gitconfig for Personal projects

   [user]
      name = "Your Personal Name"
      email = "yourpersonal@example.com"
   ```

3. **Set Up Conditional Global Configuration:** In your global `.gitconfig`, add conditional configurations based on the directory path. This way, repositories in each directory will automatically inherit the corresponding profile information.

   ```ps1
   [includeIf "gitdir:/path/to/Personal/"]
      path = "/path/to/Personal/.gitconfig"

   [includeIf "gitdir:/path/to/Work/"]
      path = "/path/to/Work/.gitconfig"

   [includeIf "gitdir:/path/to/Freelance/"]
      path = "/path/to/Freelance/.gitconfig"
   ```

4. **One-Time Setup for Automatic Profile Assignment:** Once configured, new repositories placed in these directories will automatically inherit the correct profile settings. This approach requires minimal ongoing effort and keeps profiles organized consistently across all projects.

<hr/>

Each method offers distinct advantages...

- _Method 1_ provides explicit control for each repository, ideal if you frequently switch between profiles on a single device.
- _Method 2_ offers a streamlined setup, especially suited to users managing multiple project types in dedicated directories.

### 2. Accessing Repositories

Managing multiple SSH keys for different accounts helps keep profiles organized and prevents access issues:

- **Creating SSH Keys:** Generate separate SSH keys for _Personal_ and _Work_ accounts.

  ```ps1
  ssh-keygen -t ed25519 -C "yourpersonal@example.com"
  ssh-keygen -t ed25519 -C "yourwork@example.com"
  ```

- **Configuring the SSH Config File:** Edit your `~/.ssh/config` file to associate each key with the appropriate Git hosting platform (`Github`, `Gitlab`, etc.) account. This file defines host aliases, so you can easily specify which SSH key to use per account.

  ```ps1
  # Personal account

  Host github.com-personal
   HostName github.com
   User git
   IdentityFile /path/to/your/keys/personal_key

  # Work account

  Host github.com-work
   HostName github.com
   User git
   IdentityFile /path/to/your/keys/work_key
  ```

- **Using Host Aliases:** When cloning or working with repositories, use the appropriate host alias (e.g., `github.com-personal` or `github.com-work`) to ensure the correct SSH key is used.

- **Adding SSH Key to Git Hosting Platform:** After creating your SSH keys, add the public SSH key content (the `.pub` file) to your Git hosting platform as an **_Authentication Key_**.

### 3. Maintaining Signing Keys

Configuring separate signing keys for work and personal repositories helps maintain a clear distinction in commit verification.

> **Note:** Git started providing GPG key signing support initially, but from version 2.34 onward, you can use SSH keys to sign commits. This approach is recommended over GPG for signing keys.

- **Generating Signing Keys:** The SSH keys you generated for authentication (as outlined in the [**Accessing Repositories**](#2-accessing-repositories) section) can also serve the dual purpose of signing your commits. However, if you desire a more granular approach to key management, you have the option to generate distinct keys specifically for the signing process.

  ```ps1
  ssh-keygen -t ed25519 -C "yourpersonal@example.com" # For personal account
  ssh-keygen -t ed25519 -C "yourwork@example.com"    # For work account
  ```

- **Configuring Git to Use a Specific Signing Key:** Set up your `.gitconfig` to use each profile’s specific signing key.

  To sign commits with SSH keys, Git expands the GPG signing mechanism by adding a supported format called `ssh`. The following flow outlines the steps for setting up SSH key signing:

  1. **Set the Format to SSH:**

     ```ps1
     git config gpg.format ssh
     ```

  2. **Assign the Signing Key:**

     Use your SSH key fingerprint (the content of your `.pub` file)

     ```ps1
     git config user.signingKey "YourSSHKeyFingerprint"
     ```

  3. **Manually Sign a Commit:**

     To sign any commit, use the `-S` flag when making the commit:

     ```ps1
     git commit -S -m "Your commit message"
     ```

  4. **(Optional) Enable Automatic Signing:**

     To automatically sign commits without having to use the `-S` flag each time...

     ```ps1
     git config commit.gpgSign true
     ```

- **Adding the Signing Key to Git Hosting Platform:**
  Once you have set up the local configurations, you'll need to add the key fingerprint to your Git hosting platform as a **_Signing Key_**. If you are using the same key for authentication, that key might already be added as an **_Authentication Key_**. In this case, you would simply add the same key again as a **_Signing Key_**.

#### Additional Notes

These signing configurations typically align with the Git profiles established in the [**Setting Up Local Git Profiles**](#1-setting-up-local-git-profiles) section. Here’s how to approach them based on your chosen management method:

- **For Individual Repository Management ([Method 1](#method-1-configuring-profiles-per-repository)):**

  - **Signing Configurations:**

    These can be set in either:

    - The individual repository’s `.gitconfig`
    - The global `.gitconfig`

  - **Choosing Your Approach:**

    - Use **individual repository settings** for detailed control over signing configurations specific to each project.
    - Use **global settings** for broader configurations applicable across multiple projects.

- **For Directory-Based Profile Management ([Method 2](#method-2-conditional-configuration-using-directory-based-profiles)):**

  - **Signing Settings:**

    Include signing settings in the dedicated `.gitconfig` files specific to each category to ensure seamless integration with your overall profile management strategy.

## Conclusion

These configurations ensure that each profile is properly maintained, preventing unintended mix-ups between work and personal repositories and adding an extra layer of security with signing keys.
