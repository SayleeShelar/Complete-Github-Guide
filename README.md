COMPLETE GITHUB GUIDE



This guide will help you understand how to use Git for version control and GitHub to collaborate with others on projects. We'll cover everything from installation to advanced commands.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Installing Git](#installing-git)
3. [Configuring Git](#configuring-git)
4. [Starting a New Git Project](#starting-a-new-git-project)
5. [Making Your First Commit](#making-your-first-commit)
6. [Important Git Practices](#important-git-practices)
7. [Working with a Remote Repository (GitHub)](#working-with-a-remote-repository-github)
    - [Creating a Repository on GitHub](#creating-a-repository-on-github)
    - [Linking Local Git with GitHub](#linking-local-git-with-github)
    - [Pushing Code to GitHub](#pushing-code-to-github)
    - [Cloning a Repository](#cloning-a-repository)
8. [Branching and Merging](#branching-and-merging)
9. [Undoing Changes](#undoing-changes)
10. [Working with Forks and Pull Requests](#working-with-forks-and-pull-requests)
11. [Common Workflow for Forked Repositories](#common-workflow-for-forked-repositories)
12. [Differences: Git Pull vs Git Fetch and Merge/Rebase](#differences-git-pull-vs-git-fetch-and-mergerebase)
13. [Advanced Git Concepts](#advanced-git-concepts)
14. [Common Errors and Fixes](#common-errors-and-fixes)
15. [Conclusion](#conclusion)

---

## 1. Introduction

### What is Git?
Git is a version control system used to track changes in your code and collaborate with others. It allows you to maintain a history of changes and work with others without overwriting each other’s changes.

### What is GitHub?
GitHub is a cloud-based platform that hosts Git repositories. It helps in sharing code, collaborating with others, and keeping code safe online.

---

## 2. Installing Git

### Step 1: Download Git
- Visit the official Git website at [Git Downloads](https://git-scm.com/downloads).
- Choose the installer for your operating system (Windows, macOS, Linux).

### Step 2: Install Git
- Run the installer and follow the setup instructions. For Windows, make sure to include **Git Bash**, which provides a command-line interface to use Git.

### Step 3: Verify Installation
- Open a terminal or Git Bash and run:
    ```bash
    git --version
    ```
  This should return the installed version of Git, confirming the installation.

---

## 3. Configuring Git

Before using Git, you need to configure your identity (name and email).

### Step 1: Set Your Name
```bash
git config --global user.name "Your Name"
```

### Step 2: Set Your Email
```bash
git config --global user.email "your.email@example.com"
```

### Step 3: Verify Configuration
To see your configuration:
```bash
git config --list
```

---

## 4. Starting a New Git Project

To track a project with Git, you need to initialize a repository.

### Example Scenario
Let’s assume you’re working on a project in a folder called `MyProject`.

### Step 1: Navigate to the Project Folder
Open your terminal and navigate to the project directory:
```bash
cd path/to/MyProject
```

### Step 2: Initialize a Git Repository
Run the following command:
```bash
git init
```
This creates a `.git` folder inside your project directory, which Git uses to track changes.

---

## 5. Making Your First Commit

Once the repository is initialized, you can start tracking changes.

### Step 1: Check the Status of Your Project
Before committing, **always check which branch you are on**. Run:
```bash
git branch
```
Make sure you’re on the correct branch (e.g., `main` or `develop`), especially when working on large projects.

To see which files are being tracked and which are untracked:
```bash
git status
```

### Step 2: Add Files to the Staging Area
Before committing, add files to the staging area:
```bash
git add <file-name>
```
To add all files:
```bash
git add .
```

### Step 3: Commit Your Changes
A commit saves your changes in the Git history. Each commit requires a message:
```bash
git commit -m "Initial commit - Added project files"
```

---

## 6. Important Git Practices

### Check Which Branch You Are On
- Always run `git branch` before committing to ensure you're on the correct branch.
- This prevents accidentally committing changes to the wrong branch.

---

## 7. Working with a Remote Repository (GitHub)

### Creating a Repository on GitHub

### Step 1: Create a GitHub Account
If you don't already have a GitHub account, create one at [GitHub](https://github.com).

### Step 2: Create a New Repository
- Go to GitHub and click the "New" button to create a repository.
- Give your repository a name (e.g., `MyProject`).
- Leave it as public or private, based on your preference.
- **DO NOT** initialize the repository with a README. We’ll push the code from our local project.

---

### Linking Local Git with GitHub

After creating the repository on GitHub, you need to link your local project to this remote repository.

### Step 1: Add the Remote Repository
In the terminal, inside your project directory, run:
```bash
git remote add origin https://github.com/your-username/your-repository-name.git
```

### Step 2: Push Your Code to GitHub
Now, you can push your local commits to GitHub:
```bash
git push -u origin main
```
This uploads the project from your local machine to GitHub.

---

### Cloning a Repository

If you want to download someone else’s project to your local machine:

### Step 1: Copy the Repository URL
- Go to the GitHub repository you want to clone.
- Click on the green "Code" button and copy the HTTPS URL.

### Step 2: Clone the Repository
In your terminal, run:
```bash
git clone https://github.com/username/repository-name.git
```
This will download the entire repository to your local machine.

---

## 8. Branching and Merging

### What is Branching?
Branching allows you to work on different features without affecting the main code. 

### Example Scenario:
You are adding a new feature to your project but don’t want to mess with the main branch.

### Step 1: Create a New Branch
```bash
git branch feature-branch
```

### Step 2: Switch to the New Branch
```bash
git checkout feature-branch
```

### Step 3: Make Changes and Commit
After making your changes, commit them as usual:
```bash
git commit -m "Added new feature"
```

### Step 4: Merge Changes Back to the Main Branch
Switch back to the `main` branch and merge the changes from the feature branch:
```bash
git checkout main
git merge feature-branch
```

---

## 9. Undoing Changes

### Scenario 1: Unstage a File
If you added a file by mistake, you can unstage it:
```bash
git restore --staged <file-name>
```

### Scenario 2: Revert a Commit
To undo a specific commit, use the `git reset` command:
```bash
git reset <commit-hash>
```
This removes the commit but keeps the changes in your working directory.

---

## 10. Working with Forks and Pull Requests

Forking is used to copy someone else’s repository into your GitHub account so you can make changes.

### Step 1: Fork a Repository
Go to the repository on GitHub and click the "Fork" button.

### Step 2: Clone the Forked Repository
Once the repository is forked to your account, clone it locally:
```bash
git clone https://github.com/your-username/forked-repository.git
```

### Step 3: Make Changes and Push
Make your changes, then push them to your forked repository:
```bash
git push origin main
```

### Step 4: Submit a Pull Request
On GitHub, go to your forked repository and click "Pull Request" to suggest your changes to the original repository.

---

## 11. Common Workflow for Forked Repositories

After forking and cloning a repository, it’s important to stay updated with changes from the original repository.

### Step 1: Add the Upstream Remote
The upstream remote points to the original repository:
```bash
git remote add upstream https://github.com/original-owner/repository-name.git
```

### Step 2: Fetch Changes from Upstream
Before working on a new feature, always fetch the latest changes:
```bash
git fetch upstream
```

### Step 3: Merge or Rebase Changes
After fetching, you need to incorporate the changes into your local branch.

- **Merging**:
    ```bash
    git merge upstream/main
    ```
    This

 brings the changes into your current branch, while keeping the history of the original and new changes.

- **Rebasing**:
    ```bash
    git rebase upstream/main
    ```
    This re-applies your changes on top of the new changes from upstream, creating a cleaner commit history.

### Step 4: Push Changes to Your Fork
After incorporating upstream changes, push them to your fork:
```bash
git push origin <branch>
```

---

## 12. Differences: Git Pull vs Git Fetch and Merge/Rebase

### Git Pull
- **Command**: `git pull`
- Combines both `git fetch` and `git merge`.
- Directly downloads changes and merges them into your current branch.

### Git Fetch and Merge/Rebase
- **Commands**: `git fetch`, followed by `git merge` or `git rebase`.
- **Fetch**: Downloads updates but doesn’t merge them automatically. You can manually merge or rebase afterward.
- **Merge/Rebase**: Gives you more control over how you incorporate changes, with the option to review before merging or rebasing.

#### Why use `fetch` + `merge/rebase`?
- **More control**: You can review the fetched changes before merging them into your branch.
- **Clean history**: Rebasing keeps the commit history linear and cleaner, while `merge` keeps a separate branch history.

---

### Topic 13: Advanced Git Concepts

This section introduces some advanced Git concepts that are useful for larger projects and more complex workflows.

#### 1. **Git Stash**
- Temporarily stores your changes without committing them.
- Use it when you need to switch branches but don’t want to commit incomplete work.
  
    **Command:**
    ```bash
    git stash
    ```
    To reapply the stashed changes:
    ```bash
    git stash apply
    ```

#### 2. **Git Cherry-Pick**
- Applies a specific commit from another branch onto your current branch.
  
    **Command:**
    ```bash
    git cherry-pick <commit-hash>
    ```

#### 3. **Git Reflog**
- Keeps track of all actions, even those not in the commit history (like `checkout` and `reset`).
  
    **Command:**
    ```bash
    git reflog
    ```

#### 4. **Squashing Commits**
- Combines multiple commits into one, making the history cleaner.
  
    **Command:**
    ```bash
    git rebase -i HEAD~<number-of-commits>
    ```

---

### Topic 14: Common Errors and Fixes

#### 1. **Detached HEAD State**
- Happens when you checkout a specific commit instead of a branch.
  
    **Fix:**
    ```bash
    git checkout <branch-name>
    ```

#### 2. **Merge Conflicts**
- Occur when Git cannot automatically merge changes.
  
    **Fix:**
    - Edit the conflicting files manually to resolve conflicts.
    - After resolving conflicts, run:
    ```bash
    git add <file>
    git commit
    ```

#### 3. **Forgot to Add a File Before Commit**
- If you missed adding a file and already committed:
  
    **Fix:**
    ```bash
    git add <file>
    git commit --amend
    ```

#### 4. **Pushing to the Wrong Branch**
- If you accidentally pushed to the wrong branch:
  
    **Fix:**
    ```bash
    git checkout <correct-branch>
    git push origin <correct-branch>
    ```

---


## 15. Conclusion
This guide provides a basic understanding of Git and GitHub. Always practice to get more familiar with the commands and workflows.
### Key Differences: `git pull` vs `git fetch + merge/rebase`
1. **`git pull`** does both `fetch` and `merge` in one step, automatically integrating the changes into your current branch.
2. **`git fetch`** retrieves changes from the remote repository without integrating them. You can review and decide to `merge` or `rebase` afterward, offering more control over how changes are incorporated.
