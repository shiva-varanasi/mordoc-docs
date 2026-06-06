---
title: Create a Project
description: Create a new Mordoc documentation project from the starter template.
---

A Mordoc project is a folder that contains your Markdown content, configuration files, and static assets. Mordoc provides the documentation site behavior for you, so you can focus on writing and organizing content.

The fastest way to start is with `create-mordoc-app`. It creates the project folder, copies a starter template, adds the required scripts, and installs Mordoc for you.

## Create the project

Open the terminal in your code editor, then go to the folder where you want to keep your documentation projects.

Run this command:

```bash
npx create-mordoc-app my-docs
```

Replace `my-docs` with the name you want for your documentation folder.

The command may take a little while. It creates the folder, adds the starter files, and prepares the project so you can run it.

{% callout type="note" title="What is npx?" %}
`npx` comes with npm. It downloads and runs `create-mordoc-app` without making you install it globally first.
{% /callout %}

## Wait for the success message

When the command finishes, you should see a success message in the terminal.

If you see an error, read the message carefully. Common causes are:

* The folder name already exists
* Your internet connection is unavailable
* Node.js or npm is not installed correctly

If the command succeeds, your new documentation project is ready.

## Move into the project

After the command finishes, move into the new folder:

```bash
cd my-docs
```

If you used a different project name, use that folder name instead.

## Open the folder

Open the new project folder in your code editor. You do not need to understand every file yet. In the next step, you will simply run the site and see it in your browser.

## Next step

[Run your site locally](/getting-started/run-locally).
