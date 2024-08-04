# Git Basics and Usage Guide

## Table of Contents

1. [Introduction to Git](#introduction-to-git)
2. [Setting Up Git](#setting-up-git)
3. [Basic Git Commands](#basic-git-commands)
4. [Working with Remote Repositories](#working-with-remote-repositories)
5. [Branching and Merging](#branching-and-merging)
6. [Git Hosting Services](#git-hosting-services)
   - [GitHub](#github)
   - [GitLab](#gitlab)
   - [Bitbucket](#bitbucket)
   - [Other Services](#other-services)
7. [Additional Resources](#additional-resources)

## Introduction to Git

Git is a distributed version control system designed to handle everything from small to very large projects with speed and efficiency. It allows multiple developers to work on a project simultaneously without overwriting each other's changes.

## Setting Up Git

### Installing Git

1. **Linux:**
   ```bash
   sudo apt-get install git
   ```

2. **Mac:**
   ```bash
   brew install git
   ```

3. **Windows:**
   Download and install Git from [git-scm.com](https://git-scm.com/).

### Configuring Git

Set up your user name and email address to be used with your commits.

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

You can check your configuration with:

```bash
git config --list
```

## Basic Git Commands

### Initializing a Repository

To start a new repository, navigate to your project directory and run:

```bash
git init
```

### Cloning a Repository

To clone an existing repository from a remote server, use:

```bash
git clone <repository-url>
```

### Adding Files

To add files to your repository, use:

```bash
git add <file>
```

To add all files:

```bash
git add .
```

### Staging Changes
```bash
git add <file_or_directory>
git add .
```
- Stage changes for the next commit.

### Committing
```bash
git commit -m "commit message"
```
- Commit staged changes with a message.

### Viewing Status
```bash
git status
```
- Show the working tree status.

### Viewing History
```bash
git log
```
- Show commit logs.

### Branching
```bash
git branch
git branch <branch_name>
git checkout <branch_name>
git checkout -b <new_branch_name>
```
- List branches, create a branch, switch to a branch, and create/switch to a new branch.

### Merging
```bash
git merge <branch_name>
```
- Merge changes from another branch into the current branch.

### Pushing to Remote
```bash
git remote add origin <remote_repository_url>
git push -u origin <branch_name>
git push
```
- Add a remote repository, push changes to it, and push subsequent changes.

### Pulling from Remote
```bash
git pull
```
- Fetch and integrate changes from the remote repository.

### Stashing Changes
```bash
git stash
git stash pop
```
- Save changes temporarily and retrieve them later.

### Resetting Changes
```bash
git reset --hard <commit_hash>
```
- Reset the working directory to a specific commit.

### Adding a Remote

To add a remote repository, use:

```bash
git remote add origin <repository-url>
```

### Fetching Changes

To fetch changes from the remote repository, use:

```bash
git fetch origin
```

### Pulling Changes

To pull changes from the remote repository and merge them into your local branch, use:

```bash
git pull origin <branch-name>
```

### Pushing Changes

To push your changes to the remote repository, use:

```bash
git push origin <branch-name>
```

## Branching and Merging

### Creating a Branch

To create a new branch, use:

```bash
git branch <branch-name>
```

### Switching Branches

To switch to another branch, use:

```bash
git checkout <branch-name>
```

### Merging Branches

To merge a branch into your current branch, use:

```bash
git merge <branch-name>
```

## Git Hosting Services

### GitHub

[GitHub](https://github.com/) is a web-based platform used for version control. It uses Git for source code management and is widely used for open-source projects. GitHub offers additional features such as issues, pull requests, and GitHub Actions for CI/CD.

### GitLab

[GitLab](https://gitlab.com/) is another web-based DevOps lifecycle tool that provides a Git repository manager providing wiki, issue-tracking, and CI/CD pipeline features, using an open-source license.

### Bitbucket

[Bitbucket](https://bitbucket.org/) is a Git repository management solution designed for professional teams. It provides source code repository hosting services, CI/CD, and integrates well with Atlassian products like Jira.

### Other Services

- **Azure Repos:** Part of Azure DevOps services, providing Git repositories and other DevOps tools.
- **SourceForge:** A web-based service that offers software developers a centralized online location to control and manage free and open-source software projects.

## Additional Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [GitHub Guides](https://guides.github.com/)
- [GitLab Documentation](https://docs.gitlab.com/)

