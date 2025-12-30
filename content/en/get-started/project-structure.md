---
title: Understand Project Structure
description: Learn about the files and folders in your Mordoc project and how they work together to create your documentation site.
---

A Mordoc project has a clear, organized structure that separates content, configuration, and assets. Understanding this structure helps you efficiently manage and customize your documentation.

# Project overview

```Structure
my-docs/
├── config/
│   ├── favicon.ico
│   ├── logo.png
│   ├── logo-dark.png
│   ├── sidenav.yaml
│   ├── site.json
│   └── styles/
│       ├── main.json
│       └── typography.json
├── content/
│   └── en/
│       ├── index.md
│       └── guides/
│           └── getting-started.md
├── public/
│   ├── images/
│   └── icons/
├── dist/
├── node_modules/
├── package.json
└── package-lock.json
```

## Directory breakdown

### config

The `config/` directory contains all configuration related to your documentation site. This is where you define global settings, control navigation, and add branding assets such as logos and styles.

In most cases, this is the only place where you will customize how your documentation looks and behaves.

#### Branding assets

- **`logo.png`**: Logo displayed top left section of the header. Supported formats: `.jpg`, `.jpeg`, `.png`, `.svg`.
- **`logo-dark.png`**: Logo displayed in dark mode. This is optional. When not present, `logo.png` is used for dark mode as well. Supported formats: `.jpg`, `.jpeg`, `.png`, `.svg`.
- **`favicon.ico`**: Icon that shows up on the browser tab. File name must be exactly `favicon.ico`

Replace these files with your own branding assets. Make sure the filenames remain unchanged.

{% callout type="note" title="Tip" %}
If the development server is running, stop it and run `npm run build` followed by `npm run dev` again to preview your changes.
{% /callout %}

#### site.json

**`site.json`** - The site.json file defines the identity of your documentation site. It controls global settings such as the site title, description, and metadata that apply across the entire site.

```json
{
  "title": "Photoniuum Flight Notes",
  "description": "Fantasy documentation for lightspeed travel, photonic engines, and the etiquette of outrunning causality.",
  "keywords": [
    "photoniuum",
    "lightspeed",
    "ftl",
    "photonic drive",
    "navigation",
    "field manual",
    "fictional docs"
  ],
  "baseUrl": "docs.photoniuum.com"
}
```

{% table %}
* Field
* Description
---
* `title`
* The site-wide title that appears in browser tabs and search results. Combined with individual page titles to create unique page titles.
---
* `description`
* Default description for your documentation site. Used when individual pages don't specify their own description. Helps with Search Engine Optimization (SEO) and provides context about your site's purpose.
---
* `keywords`
* Site-wide keywords array used for SEO.
---
* `baseUrl`
* The root URL of your site. Used to generate absolute URLs for canonical links and social media sharing metadata.
{% /table %}

Update this file to match the identity and purpose of your documentation site.

#### sidenav.yaml

The `sidenav.yaml` file defines the structure of your site’s side navigation.

This file controls how pages are grouped and ordered in the sidebar. In most cases, it’s best to update this file after your content is in place, so the navigation reflects the structure of your documentation.

You’ll learn how to configure this file in detail in the [Side Navigation](/configuration/sidenav) section.

#### styles

The `styles/` directory contains all styling-related configuration for your documentation site.

Mordoc comes with a default styling setup that provides a clean and usable starting point for most documentation sites.

For many projects, this default styling is sufficient for an initial version. As your documentation evolves, you can further customize the look and feel to match your brand.

Styling in Mordoc is configured at the component level. You’ll learn how to customize styles for individual components in the [Syntax & Components](/syntax-components/headings) section.


### content

The `content/` directory contains all of your documentation content, organized by language. Currently, only `en` (English) is supported. This directory is the heart of your documentation site.

This is where most of your day-to-day writing will happen.

Content in a Mordoc-powered documentation site is written primarily in [Markdown](https://en.wikipedia.org/wiki/Markdown). Mordoc inherits the full Markdown syntax and extends it with additional features.

Because Mordoc is built on top of [Markdoc](https://markdoc.dev/), it also supports the standard Markdoc syntax out of the box. The syntax for the most commonly used documentation components is described in the [Syntax & Components](/syntax-components/headings) section.

#### Structure

```
content/
└── en/                 # Language directory
    ├── index.md        # Homepage
    ├── field-manual/         # Section directory
    │   ├── engines.md
    │   └── relativity.md
    └── ship-systems/
        └── flux-sails.md
```

#### Content organization rules

1. **Language Directories**: Each language gets its own directory (e.g., `en/`, `es/`, `fr/`)
2. **Homepage**: `index.md` in the language root is your site's homepage
3. **Nested Directories**: Create subdirectories to organize related content
4. **URL Mapping**: File paths become URLs:
   - `content/en/field-manual/engines.md` → `/field-manual/engines`
   - `content/en/ship-systems/flux-sails.md` → `/ship-systems/flux-sails`

This structure makes it easy to grow your documentation without reorganizing content later.

#### Typical content file

A typical content file in Mordoc is a Markdown file with two main parts:

1. **Front matter** at the top of the file, used to define the page title and description
2. **Markdown content** below it, which makes up the body of the page

Here is a simple example:

```markdown
---
title: Photonic Core
description: A deeper look at Photoniuum’s core: channels, limiters, and the “choir” effect.
---

# Photonic Core

This is where the main content of the page goes.

You can write paragraphs, lists, code blocks, and use documentation components as needed.
```

In Mordoc, the front matter is part of the content itself:

* title is rendered as the main page heading

* description appears directly below the title as the page introduction

Everything below the front matter is rendered as the page body.

You’ll learn about available syntax and components in detail in the [Syntax & Components](/syntax-components/headings) section.

### public

The `public/` directory contains static assets such as images and icons that are used within your documentation content.

Files placed in this directory are served as-is and can be referenced directly from your Markdown files. 

### node_modules

The `node_modules/` directory is automatically created during project setup. It contains all the dependencies required to run your Mordoc project.

Although this directory is essential for the project to work, you generally do not need to look inside it or modify anything there. It is managed entirely by npm.

This directory should not be committed to version control.

### dist

The `dist/` directory is automatically generated when you run `npm run build`. It contains the compiled static version of your documentation site, ready to be deployed.

This directory includes the final HTML, CSS, JavaScript, and assets generated from your content and configuration.

{% callout % type="danger" title "Important"}
Never edit files in `dist/` manually. They're regenerated on each build.
{% /callout %}

This directory should not be committed to version control.

### package.json

Defines your project metadata and dependencies:

### package-lock.json

Locks dependency versions for consistent installations.

### .gitignore

The `.gitignore` file tells Git which files and directories should not be tracked in version control.


