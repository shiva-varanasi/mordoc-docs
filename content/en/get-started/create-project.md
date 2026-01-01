---
title: Create Your First Project
description: Create a new Mordoc documentation project using the CLI tool and explore the generated starter template.
---

Mordoc provides a CLI tool that scaffolds a complete documentation project using a pre-configured template. You will have a working documentation site up and running in minutes.

# Create a new project

In your code editor’s terminal, navigate to the directory where you want to create your project and run the following command:

```bash
npx create-mordoc-app my-docs
```

Replace `my-docs` with your preferred project name.

{% callout type="note" title="What is npx?" %}
`npx` is a package runner that comes with npm. It downloads and runs the latest version of `create-mordoc-app` without requiring a global installation.
{% /callout %}

The terminal will guide you through the project setup process.

# Navigate to your project

Once the setup is complete, a new directory named `my-docs` will be created. This directory contains all the files needed for your documentation site.

## In terminal

Navigate into your project directory by running:

```bash
cd my-docs
```

## Using your code editor GUI

You can also open the `my-docs` folder directly in your code editor's Graphical User Interface (GUI). This makes it easier to explore and understand the project structure.

# Preview the default project

You are now ready to preview the default documentation site in your browser.

Follow the steps below. You do not need to fully understand these commands right now. They will be explained in detail in the [Deployment](/deployment/build) section.

1. In your project directory, run the following command:

    ```bash
    npm run build
    ```
    This command prepares the project by generating the files needed to run the documentation site.

2. Once the build is complete, start the local development server by running:
  
    ```bash
    npm run dev
    ```

    When the server is running, open your browser and visit the URL shown in the terminal. It usually looks like this:

    ```
    http://localhost:3000
    ```

That's it. You now have a working documentation site running locally. 

At this point, all that’s left is to update the content and branding to match your needs. To do that effectively, the next step is understanding how the project is structured.

# Next steps

* [Understand the Project structure](/get-started/project-structure)