# GitHub Reference Guide 📘

A comprehensive reference guide for all things GitHub, from basic commands to advanced workflows.

## Table of Contents
- [Getting Started](#getting-started)
  - [Installation](#installation)
  - [Configuration](#configuration)
  - [Basic Git Concepts](#basic-git-concepts)
- [Essential Commands](#essential-commands)
  - [Repository Operations](#repository-operations)
  - [Branch Management](#branch-management)
  - [Commit Operations](#commit-operations)
  - [Remote Operations](#remote-operations)
- [Workflows](#workflows)
  - [Basic Workflow](#basic-workflow)
  - [Branching Strategies](#branching-strategies)
  - [Pull Request Workflow](#pull-request-workflow)
- [GitHub Features](#github-features)
  - [Issues](#issues)
  - [Projects](#projects)
  - [Actions](#actions)
  - [Pages](#pages)
- [Advanced Topics](#advanced-topics)
  - [Git Hooks](#git-hooks)
  - [Submodules](#submodules)
  - [Large File Storage](#large-file-storage)
- [Troubleshooting](#troubleshooting)
  - [Common Issues](#common-issues)
  - [Error Messages](#error-messages)
  - [Best Practices](#best-practices)

## Getting Started

### Installation

#### Windows
1. Download Git from [git-scm.com](https://git-scm.com/download/win)
2. Run the installer with default settings
3. Verify installation:
```bash
git --version
```

#### macOS
1. Install via Homebrew:
```bash
brew install git
```
2. Or download from [git-scm.com](https://git-scm.com/download/mac)

#### Linux
```bash
# Ubuntu/Debian
sudo apt-get update
sudo apt-get install git

# Fedora
sudo dnf install git
```

### Configuration

#### Basic Configuration
```bash
# Set your username
git config --global user.name "Your Name"

# Set your email
git config --global user.email "your.email@example.com"

# Check your configuration
git config --list
```

#### SSH Setup
1. Generate SSH key:
```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
```
2. Add to ssh-agent:
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```
3. Add to GitHub:
   - Copy key: `cat ~/.ssh/id_ed25519.pub`
   - Go to GitHub → Settings → SSH Keys → New SSH key
   - Paste and save

### Basic Git Concepts

#### Repository (Repo)
- A directory that contains your project work and version history
- Can be local or remote
- Created using:
```bash
# Create new repo
git init

# Clone existing repo
git clone <repository-url>
```

#### Branch
- A separate line of development
- Default branch is usually `main` or `master`
- Basic operations:
```bash
# Create branch
git branch <branch-name>

# Switch branch
git checkout <branch-name>

# Create and switch (combined)
git checkout -b <branch-name>
```

#### Commit
- A snapshot of your changes
- Has a unique identifier (hash)
- Basic usage:
```bash
# Stage changes
git add <file>

# Commit changes
git commit -m "Commit message"

# Stage and commit all changes
git commit -am "Commit message"
```

## Essential Commands

### Repository Operations
```bash
# Initialize repository
git init

# Clone repository
git clone <url>

# Check repository status
git status

# View commit history
git log

# Show changes
git diff
```

### Branch Management
```bash
# List branches
git branch

# Create branch
git branch <name>

# Delete branch
git branch -d <name>

# Force delete branch
git branch -D <name>

# Rename current branch
git branch -m <new-name>
```

### Commit Operations
```bash
# Stage files
git add <file>
git add .  # Stage all changes

# Commit
git commit -m "Message"

# Amend last commit
git commit --amend

# Reset to commit
git reset <commit-hash>
git reset --hard <commit-hash>  # Discard changes
```

### Remote Operations
```bash
# Add remote
git remote add <name> <url>

# List remotes
git remote -v

# Push changes
git push <remote> <branch>

# Pull changes
git pull <remote> <branch>

# Fetch changes
git fetch <remote>
```

## Workflows

### Basic Workflow
1. Check status: `git status`
2. Pull latest changes: `git pull`
3. Create/switch branch: `git checkout -b feature-branch`
4. Make changes
5. Stage changes: `git add .`
6. Commit changes: `git commit -m "Add feature"`
7. Push changes: `git push origin feature-branch`
8. Create pull request on GitHub

### Branching Strategies

#### Git Flow
- Main branches:
  - `main` / `master`: Production code
  - `develop`: Development code
- Supporting branches:
  - `feature/*`: New features
  - `release/*`: Release preparation
  - `hotfix/*`: Production fixes

#### GitHub Flow
1. Create branch from `main`
2. Add commits
3. Open pull request
4. Review and discuss
5. Deploy and test
6. Merge to `main`

### Pull Request Workflow
1. Fork repository
2. Clone fork: `git clone <fork-url>`
3. Create feature branch
4. Make changes
5. Push to fork
6. Create pull request
7. Address review comments
8. Merge when approved

## GitHub Features

### Issues
- Bug tracking
- Feature requests
- Task management
- Templates available
- Labels and milestones
- Assignees and mentions

### Projects
- Project management boards
- Kanban-style organization
- Issue/PR integration
- Automated workflows
- Custom fields and views

### Actions
- Automated workflows
- CI/CD pipelines
- Event-driven automation
- Community marketplace
- Self-hosted runners

### Pages
- Static site hosting
- Documentation hosting
- Project websites
- Custom domains
- Jekyll integration

## Advanced Topics

### Git Hooks
- Pre-commit hooks
- Post-commit hooks
- Pre-push hooks
- Custom script integration
- Husky for Node.js projects

### Submodules
```bash
# Add submodule
git submodule add <url>

# Initialize submodules
git submodule init

# Update submodules
git submodule update
```

### Large File Storage
```bash
# Install Git LFS
git lfs install

# Track large files
git lfs track "*.psd"

# Push using LFS
git lfs push origin main
```

## Troubleshooting

### Common Issues
- Merge conflicts
- Detached HEAD state
- Authentication issues
- Large file problems
- Permission denied

### Error Messages
- "remote: Permission to ... denied"
  - Check SSH keys and permissions
- "fatal: refusing to merge unrelated histories"
  - Use `--allow-unrelated-histories`
- "fatal: not a git repository"
  - Check if you're in the correct directory
  - Run `git init` if needed

### Best Practices
- Commit early and often
- Write meaningful commit messages
- Keep branches updated
- Review before pushing
- Use `.gitignore` properly
- Document your workflow

---

## Additional Resources
- [GitHub Docs](https://docs.github.com)
- [GitHub Skills](https://skills.github.com)
- [GitHub Guides](https://guides.github.com)
- [Git Book](https://git-scm.com/book/en/v2)
- [GitHub Community](https://github.community)

## Contributing
Feel free to contribute to this reference guide by opening a pull request with your suggestions and improvements.

## License
This reference guide is available under the [MIT License](LICENSE).
