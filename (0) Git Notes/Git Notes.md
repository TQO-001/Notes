## Git Notes

### 1. Introduction to Git

**What is Git?** Git is a distributed version control system that helps developers track changes in their codebase, collaborate with others, and maintain a history of the project’s development. It is widely used in software development to ensure efficient collaboration and proper version management.

**Key Features:**

- **Version Tracking:** Tracks changes in files over time.
- **Collaboration:** Allows multiple developers to work on the same project without overwriting each other's work.
- **Branching and Merging:** Provides a way to work on isolated features or bug fixes without affecting the main codebase.
- **Distributed:** Every developer has a full copy of the repository, making collaboration more resilient.

---

### 2. Setting Up Git

**Configuration Commands:** These commands set up your Git environment.

- **Set Username:**
    
    ```bash
    git config --global user.name "Your Name"
    ```
    
    This sets your name for all commits made on your system.
    
- **Set Email:**
    
    ```bash
    git config --global user.email "your.email@example.com"
    ```
    
    Used to associate your commits with your email address.
    
- **View Configurations:**
    
    ```bash
    git config --list
    ```
    
    Lists all the configurations currently active in Git.
    

---

### 3. Initializing a Repository

**Command:**

```bash
git init
```

**What It Does:**

- Creates a new empty Git repository in the current directory.
- A hidden `.git` folder is created, which contains all version control information.

**Why It Matters:** Initialization is required before Git can track changes in your project.

---

### 4. Adding and Committing Changes

**Adding Changes to Staging Area:**

- Add specific files:
    
    ```bash
    git add <file>
    ```
    
- Add all files in the directory:
    
    ```bash
    git add .
    ```
    

**Why It Matters:** The `git add` command moves changes to the "staging area," a temporary holding space for changes that you intend to include in the next commit.

**Committing Changes:**

- Basic commit:
    
    ```bash
    git commit -m "Your commit message"
    ```
    
    Saves the staged changes to the repository.
    
- Commit all changes without adding:
    
    ```bash
    git commit -am "Your commit message"
    ```
    
    Combines `git add` and `git commit` for tracked files only.
    

**What It Does:** Commits create a snapshot of the changes in the project at a specific point in time. Commit messages explain the purpose of the changes.

---

### 5. Working with Branches

**Branches:** Branches are used to create isolated work environments for new features or fixes.

- **Create a New Branch:**
    
    ```bash
    git branch <branch-name>
    ```
    
    Creates a new branch but doesn’t switch to it.
    
- **Switch to a Branch:**
    
    ```bash
    git checkout <branch-name>
    ```
    
    Switches your working directory to the specified branch.
    
- **Create and Switch:**
    
    ```bash
    git checkout -b <branch-name>
    ```
    
    Combines branch creation and switching into a single command.
    

**Merging Branches:**

- Merge changes from another branch into the current branch:
    
    ```bash
    git merge <branch-name>
    ```
    
- Resolving Conflicts: During a merge, Git may encounter conflicts. Edit the conflicting files manually, then stage and commit them to complete the merge.

---

### 6. Remote Repositories

**Connecting to a Remote Repository:**

- **Add a Remote Repository:**
    
    ```bash
    git remote add origin <repository-url>
    ```
    
    Associates a remote repository (like GitHub) with your local repository. “Origin” is the default name for the remote.
    
- **View Remotes:**
    
    ```bash
    git remote -v
    ```
    
    Lists the URLs of the remote repositories linked to your project.
    

**Pushing Changes:**

- Push changes to the remote repository:
    
    ```bash
    git push origin <branch-name>
    ```
    
    Uploads your commits to the specified branch on the remote.

**Pulling Changes:**

- Pull changes from the remote repository:
    
    ```bash
    git pull origin <branch-name>
    ```
    
    Fetches and merges updates from the specified branch on the remote.

---

### 7. Stashing Changes

**Why Stashing is Useful:** When you need to temporarily save changes that you’re not ready to commit, stashing allows you to set them aside.

- **Save Changes to a Stash:**
    
    ```bash
    git stash
    ```
    
- **View Stashed Changes:**
    
    ```bash
    git stash list
    ```
    
- **Apply Stashed Changes:**
    
    ```bash
    git stash apply
    ```
    
- **Remove Applied Stash:**
    
    ```bash
    git stash drop
    ```
    

---

### 8. Undoing Changes

**Unstage Files:**

- Remove a file from the staging area without deleting it:
    
    ```bash
    git reset <file>
    ```
    

**Undo Last Commit:**

- Keep changes but undo the commit:
    
    ```bash
    git reset --soft HEAD~1
    ```
    
- Discard changes completely:
    
    ```bash
    git reset --hard HEAD~1
    ```
    

**Discard Uncommitted Changes in a File:**

- Revert a file to the last committed state:
    
    ```bash
    git checkout -- <file>
    ```
    

---

### 9. Advanced Git Concepts

**Rebasing:**

- Reapply commits from one branch onto another:
    
    ```bash
    git rebase <branch>
    ```
    
    Used to create a cleaner commit history.

**Interactive Rebasing:**

- Squash multiple commits into one:
    
    ```bash
    git rebase -i HEAD~<number-of-commits>
    ```
    

**Tagging:**

- Add a version tag to a specific commit:
    
    ```bash
    git tag -a <tag-name> -m "Tag message"
    ```
    
- Push tags to remote:
    
    ```bash
    git push origin <tag-name>
    ```
    

---

### 10. Common Git Workflows

**Feature Branch Workflow:**

1. Create a new branch for the feature.
2. Make changes and commit them.
3. Push the branch to the remote repository.
4. Create a pull request (PR) to merge changes into the main branch.

**Git Flow:**

1. Main branch for releases.
2. Develop branch for integrating new features.
3. Feature branches for individual features.
4. Release branches for preparing a release.
5. Hotfix branches for emergency fixes.

---

These notes provide a comprehensive overview of Git's functionality. Expand specific sections as needed for deeper study!