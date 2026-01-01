---
title: Side Navigation
description: Configure the side navigation menu for your documentation site using sidenav.yaml.
---

The side navigation defines the primary structure of your documentation site. It is configured using a single file: `config/sidenav.yaml`. This file controls the order, hierarchy, and grouping of all pages in your documentation.

# Basic Configuration

Below is a simple example of a side navigation configuration:

```yaml
- label: Home
  path: /
- label: Flight School
  path: /flight-school
  children:
    - label: Primer — What “Lightspeed” Means Here
      path: /flight-school/primer
    - label: Navigation — Folding a Straight Line
      path: /flight-school/navigation
```

Each item in the file represents a navigation entry in the sidebar.

# Navigation Item Properties

Every navigation item supports the following properties:

{% table %}
* Property
* Required
* Description
---
* label
* Yes
* Display text for the navigation item
---
* path
* Conditional
* URL path that links to a page
---
* children
* No
* List of nested navigation items
---
{% /table %}

**Rules:**

* `label` is always required.
* `path` is required only if the item should link to a page.
* `children` is optional and used to create nested navigation.

# Navigation Patterns

## Page with Content

A basic navigation item that links directly to a page:

```yaml
- label: Flight School
  path: /flight-school
```

This maps to:

```
content/en/flight-school.md
```

## Parent with Content and Children

A parent item can have its own page and child pages.

```yaml
- label: Flight School
  path: /flight-school
  children:
    - label: Primer — What “Lightspeed” Means Here
      path: /flight-school/primer
    - label: Navigation — Folding a Straight Line
      path: /flight-school/navigation
```

**File structure:**

```
content/en/
├── flight-school.md
└── flight-school/
    ├── primer.md
    └── navigation.md
```

The parent label links to `/flight-school`, while child items link to their respective pages.

## Parent as Label Only

A parent can also be used purely as a visual grouping, without its own page.

```yaml
- label: Prerequisites
  children:
    - label: Install Node.js
      path: /prerequisites/nodejs
    - label: Install Git
      path: /prerequisites/git
```

**Key difference:**

The parent does not define a `path`.

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

Mordoc supports deeper nesting when needed:

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
Although deep nesting is supported, avoid going beyond three levels to maintain usability and clarity.
{% /callout %}

# Path Mapping

Paths defined in `sidenav.yaml` map directly to markdown files in your content directory.

{% table %}
* Navigation Path
* Content File
---
* /
* content/en/index.md
---
* /guides
* content/en/guides.md
---
* /guides/intro
* content/en/guides/intro.md
---
* /api/reference
* content/en/api/reference.md
---
{% /table %}

**Path rules:**

* Paths must start with `/`
* Do not include `.md`
* Match the folder structure under `content/`
* Use lowercase letters and hyphens

# Styling the Side Navigation

If you want to customize side navigation colors to better match your brand, you can do so by adding a `sidenav.json` file under the `config/styles/` directory.

This file allows you to control how side navigation active items appear in both light and dark modes.

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

## Available Style Variables

{% table %}
* Variable
* Description
* Example HEX value
---
* `navHoverBackground`
* Background color on hovering a sidenav item in light mode
* `#E5E5E5`
---
* `navHoverBackgroundDark`
* Background color on hovering a sidenav item in dark mode
* `#1F1F1F`
---
* `navActiveBackground`
* Background color of an active sidenav item in light mode
* `#E5E5E5`
---
* `navActiveBackgroundDark`
* Background color of an active sidenav item in dark mode
* `#1F1F1F`
---
* `navActiveTextColorLight`
* Text color of an active sidenav item in light mode
* `#171717`
---
* `navActiveTextColorDark`
* Text color of an active sidenav item in dark mode
* `#FAFAFA`
---
{% /table %}

