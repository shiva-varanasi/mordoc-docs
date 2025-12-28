---
title: Creating Your First Project
description: Create a new Mordoc documentation project using the CLI tool and explore the generated starter template.
---

# Creating Your First Project

Mordoc provides a CLI tool that scaffolds a complete documentation project with a pre-configured template. You'll have a working documentation site in minutes.

## Create a New Project

Use the `create-mordoc-app` command to generate a new project:

```bash
npx create-mordoc-app my-docs
```

Replace `my-docs` with your preferred project name.

{% callout type="note" title="What is npx?" %}
`npx` is a package runner tool that comes with npm. It downloads and executes the latest version of `create-mordoc-app` without requiring a global installation.
{% /callout %}

## Interactive Setup

The CLI will guide you through the setup process:

1. **Project Name**: Confirm or modify the project name
2. **Template Selection**: Choose a starter template (default template is recommended for beginners)
3. **Install Dependencies**: The tool will automatically install required npm packages

## Example Output

```bash
$ npx create-mordoc-app my-docs

✓ Creating Mordoc project...
✓ Copying template files...
✓ Installing dependencies...

Success! Created my-docs at /path/to/my-docs

Inside that directory, you can run several commands:

  npm run dev
    Starts the development server

  npm run build
    Builds the site for production

  npm run preview
    Previews the production build locally

Get started by typing:

  cd my-docs
  npm run dev
```

## Navigate to Your Project

```bash
cd my-docs
```

## Start the Development Server

Launch the local development server:

```bash
npm run dev
```

Your documentation site will be available at:

```
http://localhost:3000
```

The development server includes:

- **Hot Reload**: Changes to markdown files automatically refresh the browser
- **Live Preview**: See your edits in real-time
- **Error Reporting**: Console errors for syntax issues

{% callout type="warning" %}
Keep the development server running while you work. Press `Ctrl+C` to stop it when you're done.
{% /callout %}

## What Gets Created

The `create-mordoc-app` command generates a complete project structure:

```
my-docs/
├── config/
│   ├── sidenav.yaml
│   ├── site.json
│   └── styles/
│       ├── main.json
│       └── typography.json
├── content/
│   └── en/
│       └── index.md
├── public/
│   ├── images/
│   └── icons/
├── package.json
└── node_modules/
```

## Key Directories

| Directory | Purpose |
|---|---|
| `config/` | Configuration files for navigation, styling, and site settings |
| `content/` | Your markdown documentation files |
| `public/` | Static assets like images, icons, and custom files |
| `node_modules/` | Dependencies (auto-generated, don't edit) |

## Understanding the Template

The starter template includes:

- **Sample Content**: Example markdown files demonstrating Mordoc features
- **Pre-configured Navigation**: A working sidenav structure
- **Default Styling**: Professional theme with customizable colors
- **Example Assets**: Sample images and icons

You can modify or replace any of these files to match your documentation needs.

## Customize Your Site

### Update Site Information

Edit `config/site.json` to set your site metadata:

```json
{
  "title": "My Documentation",
  "description": "Documentation for my awesome project",
  "baseUrl": "https://docs.myproject.com",
  "language": "en"
}
```

### Add Your Logo

Replace the default logo files in `config/`:

- `logo.png` - Light mode logo
- `logo-dark.png` - Dark mode logo
- `favicon.ico` - Browser favicon

### Start Writing Content

Create new markdown files in `content/en/` and update `config/sidenav.yaml` to add them to your navigation.

{% callout type="note" title="Next Step" %}
Learn about the [project structure](/get-started/project-structure) to understand how all these pieces work together.
{% /callout %}

## Next Steps

Now that your project is created:

1. [Understand the Project Structure](/get-started/project-structure)
2. [Learn Markdown Syntax](/syntax-components/headings)
3. [Configure Navigation](/configuration/sidenav)

