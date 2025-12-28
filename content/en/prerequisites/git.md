---
title: Install Git
description: Install Git for version control and collaboration on your Mordoc documentation.
---

# Install Git

Git is a version control system that helps you track changes to your documentation, collaborate with others, and deploy your site. While not strictly required to use Mordoc, Git is highly recommended for managing your documentation project.

## Why Use Git?

- **Version History**: Track every change to your documentation
- **Collaboration**: Work with team members on the same documentation
- **Backup**: Keep your documentation safe in remote repositories
- **Deployment**: Many hosting platforms integrate with Git for automatic deployments

## Download Git

Visit the official Git website:

[git-scm.com](https://git-scm.com/)

## Installation Instructions

### Windows

1. Download Git for Windows from git-scm.com
2. Run the installer
3. Recommended settings during installation:
   - **Editor**: Select your preferred editor (VS Code is a good choice)
   - **PATH environment**: "Git from the command line and also from 3rd-party software"
   - **Line ending conversions**: "Checkout Windows-style, commit Unix-style line endings"
   - **Terminal emulator**: "Use Windows' default console window"
4. Complete the installation
5. Restart your terminal

### macOS

**Option 1: Using Homebrew (Recommended)**
```bash
brew install git
```

**Option 2: Using Xcode Command Line Tools**
```bash
xcode-select --install
```

**Option 3: Official Installer**
Download the macOS installer from git-scm.com and run it.

### Linux

**Ubuntu/Debian:**
```bash
sudo apt-get update
sudo apt-get install git
```

**Fedora/RHEL:**
```bash
sudo dnf install git
```

**Arch Linux:**
```bash
sudo pacman -S git
```

## Verify Installation

Check that Git is installed correctly:

```bash
git --version
```

Expected output: `git version 2.x.x` or higher

## Configure Git

Before using Git, configure your identity:

```bash
# Set your name
git config --global user.name "Your Name"

# Set your email
git config --global user.email "your.email@example.com"
```

Verify your configuration:

```bash
git config --list
```

{% callout type="note" title="First Time Using Git?" %}
These settings are used to identify who made changes in your project history. Use your real name and email address.
{% /callout %}

## Optional: Configure Default Branch Name

Set the default branch name to `main`:

```bash
git config --global init.defaultBranch main
```

## Common Git Commands for Documentation

Here are the Git commands you'll use most often with Mordoc:

### Initialize a Repository

```bash
# In your project directory
git init
```

### Track Changes

```bash
# See what files have changed
git status

# Add files to staging
git add .

# Commit changes
git commit -m "Update documentation"
```

### Connect to GitHub

```bash
# Add remote repository
git remote add origin https://github.com/username/repo.git

# Push changes
git push -u origin main
```

## Git GUI Clients (Optional)

If you prefer a visual interface:

| Client | Platform | Notes |
|---|---|---|
| **GitHub Desktop** | Windows, macOS | Simple and beginner-friendly |
| **GitKraken** | Windows, macOS, Linux | Feature-rich with visual commit graph |
| **Sourcetree** | Windows, macOS | Free from Atlassian |
| **VS Code** | All platforms | Built-in Git support |

## Troubleshooting

### Command Not Found

If Git is not recognized:

1. Restart your terminal
2. Check if Git is in your PATH
3. Reinstall Git and ensure "Add to PATH" is selected

### Line Ending Issues

If you see warnings about line endings:

```bash
# Windows users
git config --global core.autocrlf true

# macOS/Linux users
git config --global core.autocrlf input
```

{% callout type="warning" %}
When collaborating across different operating systems, consistent line ending configuration prevents unnecessary changes in version control.
{% /callout %}

## Next Steps

With Git installed, you're ready to:

- [Create your first project](/get-started/creating-project) - Build your documentation site
- [Version Control guide](/deployment/version-control) - Learn Git workflows for documentation

