---
title: Install Node.js
description: Install Node.js and npm to run Mordoc and build your documentation site.
---

# Install Node.js

Mordoc requires Node.js to build and preview your documentation. Node.js includes npm (Node Package Manager), which you'll use to install and run Mordoc.

## System Requirements

- **Node.js version**: 18.0.0 or higher
- **npm version**: 9.0.0 or higher (included with Node.js)

## Download Node.js

Visit the official Node.js website:

[nodejs.org](https://nodejs.org/)

You'll see two versions available:

- **LTS (Long Term Support)**: Recommended for most users
- **Current**: Latest features, less stable

{% callout type="note" title="Recommendation" %}
Download the **LTS version** for maximum stability and compatibility with Mordoc.
{% /callout %}

## Installation Instructions

### Windows

1. Download the Windows Installer (.msi) from nodejs.org
2. Run the installer
3. Follow the installation wizard:
   - Accept the license agreement
   - Choose installation location (default is fine)
   - Keep default features selected
   - Check "Automatically install necessary tools" if prompted
4. Click "Install"
5. Restart your terminal after installation

### macOS

**Option 1: Official Installer**
1. Download the macOS Installer (.pkg) from nodejs.org
2. Run the installer
3. Follow the installation wizard
4. Restart your terminal

**Option 2: Using Homebrew**
```bash
brew install node
```

### Linux

**Ubuntu/Debian:**
```bash
# Using NodeSource repository
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

**Fedora/RHEL:**
```bash
sudo dnf install nodejs
```

**Arch Linux:**
```bash
sudo pacman -S nodejs npm
```

## Verify Installation

After installation, verify that Node.js and npm are installed correctly:

```bash
node --version
```

Expected output: `v18.x.x` or higher

```bash
npm --version
```

Expected output: `9.x.x` or higher

{% callout type="warning" %}
If the commands are not recognized, you may need to restart your terminal or add Node.js to your system PATH.
{% /callout %}

## Update npm (Optional)

To update npm to the latest version:

```bash
npm install -g npm@latest
```

## Troubleshooting

### Command Not Found

If you get a "command not found" error:

1. Restart your terminal completely
2. Verify Node.js is in your PATH:
   ```bash
   # Windows (PowerShell)
   $env:Path -split ';' | Select-String node
   
   # macOS/Linux
   echo $PATH | grep node
   ```

### Permission Issues (macOS/Linux)

If you encounter permission errors when installing packages globally:

```bash
# Fix npm permissions
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.profile
source ~/.profile
```

## Next Steps

With Node.js installed, you're ready to:

- [Install Git](/prerequisites/git) - Set up version control
- [Create your first project](/get-started/creating-project) - Start building with Mordoc

