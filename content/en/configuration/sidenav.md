---
title: Side Navigation
description: Configure the side navigation menu for your documentation site using sidenav.yaml.
---

The side navigation provides the primary navigation structure for your documentation site. Configure it using the `config/sidenav.yaml` file to create a hierarchical menu with parent pages and child pages.

# Configuration File

The navigation is defined in `config/sidenav.yaml`:

```yaml
- label: Home
  path: /

- label: Getting Started
  path: /get-started
  children:
    - label: Installation
      path: /get-started/installation
    - label: First Steps
      path: /get-started/first-steps
```

# Basic Navigation Item

Each navigation item requires a `label`:

```yaml
- label: Overview
  path: /overview
```

## Properties

| Property | Type | Required | Description |
|----------|------|:--------:|-------------|
| `label` | string | ✓ | Display text for the navigation item |
| `path` | string | Conditional | URL path to the page |
| `children` | array | ✗ | Nested child navigation items |

# Navigation Patterns

## Page with Content

A navigation item that links to a specific page:

```yaml
- label: FAQ
  path: /faq
```

This links to `content/en/faq.md`.

## Parent with Content and Children

A parent page that has its own content AND child pages:

```yaml
- label: Guides
  path: /guides
  children:
    - label: Beginner Guide
      path: /guides/beginner
    - label: Advanced Guide
      path: /guides/advanced
```

**File structure:**
```
content/en/
├── guides.md          # Parent page content
└── guides/
    ├── beginner.md    # Child page
    └── advanced.md    # Child page
```

## Parent as Label Only

A parent that groups child pages but has no content of its own:

```yaml
- label: Prerequisites
  children:
    - label: Install Node.js
      path: /prerequisites/nodejs
    - label: Install Git
      path: /prerequisites/git
```

**Notice:** No `path` property on the parent. It's just a section label.

**File structure:**
```
content/en/
└── prerequisites/
    ├── nodejs.md
    └── git.md
```

# Nested Navigation

## Two-Level Navigation

```yaml
- label: API Reference
  path: /api
  children:
    - label: Authentication
      path: /api/authentication
    - label: Users
      path: /api/users
    - label: Projects
      path: /api/projects
```

## Multi-Level Navigation

Mordoc supports deep nesting:

```yaml
- label: Documentation
  path: /documentation
  children:
    - label: Getting Started
      path: /documentation/getting-started
      children:
        - label: Installation
          path: /documentation/getting-started/installation
        - label: Configuration
          path: /documentation/getting-started/configuration
    - label: Advanced
      path: /documentation/advanced
```

{% callout type="warning" %}
While deep nesting is supported, avoid going more than 3 levels deep for better user experience.
{% /callout %}

# Path Mapping

Paths in `sidenav.yaml` map to markdown files in your content directory:

| Navigation Path | Content File |
|-----------------|--------------|
| `/` | `content/en/index.md` |
| `/guides` | `content/en/guides.md` |
| `/guides/intro` | `content/en/guides/intro.md` |
| `/api/reference` | `content/en/api/reference.md` |

**Rules:**
- Paths start with `/`
- No `.md` extension
- Match the content directory structure
- Use lowercase with hyphens

# Complete Example

```yaml
# Homepage
- label: Home
  path: /

# Single page
- label: Overview
  path: /overview

# Parent with content + children
- label: Get Started
  path: /get-started
  children:
    - label: Creating Project
      path: /get-started/creating-project
    - label: Project Structure
      path: /get-started/project-structure

# Parent as label only
- label: Prerequisites
  children:
    - label: Code Editor
      path: /prerequisites/code-editor
    - label: Node.js
      path: /prerequisites/nodejs
    - label: Git
      path: /prerequisites/git

# Multiple sections
- label: Syntax & Components
  children:
    - label: Headings
      path: /syntax-components/headings
    - label: Links
      path: /syntax-components/links
    - label: Images
      path: /syntax-components/images
    - label: Lists
      path: /syntax-components/lists
    - label: Tables
      path: /syntax-components/tables
    - label: Code Blocks
      path: /syntax-components/code-blocks
    - label: Callouts
      path: /syntax-components/callouts
    - label: Cards
      path: /syntax-components/cards

# Styling Navigation

Customize navigation appearance through configuration.

Edit `config/styles/main.json` (create if it doesn't exist):

```json
{
  "navHoverBackgroundLight": "#E5E5E5",
  "navHoverBackgroundDark": "#1F1F1F",
  "navActiveBackgroundLight": "#E5E5E5",
  "navActiveBackgroundDark": "#1F1F1F",
  "navActiveTextColorLight": "#171717",
  "navActiveTextColorDark": "#FAFAFA"
}
```

## Available Style Variables for Side Navigation

| Variable | Description | Default |
|----------|-------------|---------|
| `navHoverBackgroundLight` | Hover background (light mode) | `#E5E5E5` |
| `navHoverBackgroundDark` | Hover background (dark mode) | `#1F1F1F` |
| `navActiveBackgroundLight` | Active item background (light) | `#E5E5E5` |
| `navActiveBackgroundDark` | Active item background (dark) | `#1F1F1F` |
| `navActiveTextColorLight` | Active item text color (light) | `#171717` |
| `navActiveTextColorDark` | Active item text color (dark) | `#FAFAFA` |

{% callout type="note" %}
These variables go in `config/styles/main.json`, not in a separate sidenav.json file.
{% /callout %}

# Next Steps

- [Table of Contents](/configuration/toc) - Configure the page TOC
- [Search](/configuration/search) - Set up search functionality
- [Branding](/configuration/branding) - Customize logo and colors