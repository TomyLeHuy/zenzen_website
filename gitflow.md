# Project Git Workflow

This document outlines the standard Git workflow for our project. Adhering to these steps will help us maintain a clean and stable codebase, minimize merge conflicts, and ensure a structured development process.

***

## Branch Strategy

Our repository uses two primary, long-lived branches:

* **`main`**: This branch represents our production-ready, stable code. It should always be deployable.
* **`development`**: This is our main integration branch. All new feature branches are created from and merged into this branch.

***

## The Workflow: Merge-Down, Merge-Up

All new features and bug fixes will follow this process to ensure a clean commit history and local conflict resolution.

### 1. Create Your Feature Branch from `development`

Always start by ensuring your local `development` branch is up to date with the remote repository. Then, create a new feature branch for your work. Please use the naming convention `feature/your-feature-name` for consistency.

```bash
# Switch to the development branch
git checkout development

# Pull the latest changes from the remote
git pull origin development

# Create your new feature branch
git checkout -b feature/your-feature-name
```

### 2. Update Your Branch Before Merging

Before you create a pull request to merge your feature into the `development` branch, you must first merge the latest changes from `development` into your feature branch. 
This step is critical for resolving any conflicts locally.

```bash
# Switch back to the development branch
git checkout development

# Pull the latest changes
git pull origin development

# Switch back to your feature branch
git checkout feature/your-feature-name

# Merge the updated development branch into your feature branch
git merge development
```

### 3. Merge Your Feature into `development`

Once you have completed your feature and have successfully merged the latest changes from `development` into your feature branch (and resolved any conflicts), you can proceed to create a pull request to merge your feature branch back into the `development` branch.

Following this workflow ensures that the `development` branch remains stable, with all conflicts handled locally within the feature branches. This is in the best interest of all team members and the project.

Sources and further information on [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)





