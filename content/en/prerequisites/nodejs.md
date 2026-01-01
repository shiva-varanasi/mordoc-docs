---
title: Install Node.js
description: Install Node.js and npm to run Mordoc and build your documentation site.
---

Before you can run Mordoc, you need **Node.js** installed on your system. Don’t worry if this sounds technical at first. You don’t need to know how Node.js works internally to use Mordoc.

This page explains what Node.js and npm are in simple terms, and then walks you through installing them.

# What is Node.js?

Node.js is a runtime environment that lets you run JavaScript programs on your computer.

It allows Mordoc to:

* Run locally on your machine
* Generate your documentation website
* Manage dependencies and tooling behind the scenes

You won’t be writing JavaScript or building applications. Node.js is just something Mordoc needs in order to work.


# What is npm?

**npm** stands for *Node Package Manager*.

It comes bundled with Node.js and is used to:

* Install tools and packages (like Mordoc)
* Run predefined commands
* Keep dependencies up to date

You don’t need to install npm separately. If Node.js is installed, npm is already included.

# Download Node.js

1. Visit the official Node.js website: [https://nodejs.org](https://nodejs.org)
2. Download the **LTS (Long Term Support)** version. This is the recommended and most stable option.

Choose the installer for your operating system:

* **Windows**: Download the Windows installer
* **macOS**: Download the macOS installer
* **Linux**: Use the official package for your distribution or follow the Linux installation instructions on the website

# Install Node.js

Run the installer and follow the recommended options in the installation wizard.

For most users, the default settings are correct. You do not need to customize anything.

# Verify the installation

After installation is complete, verify that Node.js is installed correctly.

1. Open your code editor
2. Open the built-in terminal

   * In VS Code, you can open it from the menu: **Terminal → New Terminal**
3. Run the following command:

```bash
node -v
```

If Node.js is installed correctly, you should see a version number printed to the screen.

You can also verify npm by running:

```bash
npm -v
```

# If the command is not found

If you see a message like `command not found` or `node is not recognized`, it usually means Node.js is not available in your system’s PATH.

* On **Windows**, restarting your computer often resolves this
* On **macOS** and **Linux**, this is rare when using the official installer

If the issue persists, reinstall Node.js using the official installer and make sure you accept the default options.

# Next steps

- [Install Git](/prerequisites/git)
