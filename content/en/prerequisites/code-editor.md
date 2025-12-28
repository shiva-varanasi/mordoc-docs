---
title: Install a Code Editor
description: Set up Visual Studio Code or your preferred code editor for working with Mordoc documentation.
---

# Install a Code Editor

To create and edit markdown files for your Mordoc documentation, you'll need a code editor. This guide covers Visual Studio Code, but you can use any code editor or IDE you prefer.

## Visual Studio Code (Recommended)

Visual Studio Code (VS Code) is a free, open-source code editor with excellent markdown support.

### Download VS Code

1. Visit [code.visualstudio.com](https://code.visualstudio.com/)
2. Download the installer for your operating system:
   - **Windows**: Download the Windows installer
   - **macOS**: Download the macOS installer
   - **Linux**: Download the appropriate package (.deb, .rpm, or .snap)

### Install VS Code

**Windows:**
```bash
# Run the downloaded installer
# Follow the installation wizard
# Check "Add to PATH" during installation
```

**macOS:**
```bash
# Open the downloaded .dmg file
# Drag VS Code to Applications folder
```

**Linux (Ubuntu/Debian):**
```bash
sudo dpkg -i code_*.deb
sudo apt-get install -f
```

### Verify Installation

Open a terminal and run:

```bash
code --version
```

You should see the version number displayed.

## Recommended Extensions for Markdown

Once VS Code is installed, consider adding these helpful extensions:

| Extension | Purpose |
|---|---|
| **Markdown All in One** | Keyboard shortcuts, table of contents, and preview |
| **markdownlint** | Linting and style checking for markdown |
| **Prettier** | Code formatting for consistent style |

### Installing Extensions

1. Open VS Code
2. Click the Extensions icon in the sidebar (or press `Ctrl+Shift+X`)
3. Search for the extension name
4. Click "Install"

{% callout type="note" title="Markdown Preview" %}
VS Code has built-in markdown preview. Press `Ctrl+Shift+V` (or `Cmd+Shift+V` on macOS) to preview your markdown files.
{% /callout %}

## Alternative Code Editors

Mordoc works with any text editor. Here are some popular alternatives:

- **Sublime Text**: Lightweight and fast
- **Atom**: Hackable text editor from GitHub
- **IntelliJ IDEA**: Full-featured IDE with markdown support
- **Notepad++**: Windows-only, lightweight option
- **Vim/Neovim**: Terminal-based editors for power users

Choose the editor you're most comfortable with. All you need is the ability to create and edit `.md` (markdown) and `.yaml` files.

## Next Steps

Now that you have a code editor installed, proceed to:

- [Install Node.js](/prerequisites/nodejs) - Required for running Mordoc
- [Install Git](/prerequisites/git) - Recommended for version control

