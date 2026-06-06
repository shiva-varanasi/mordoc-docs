---
title: Side Navigation
description: Configure the sidebar links that help readers move through your documentation.
---

The side navigation is the list of links shown beside normal documentation pages.

You already used it in [Navigation Basics](/getting-started/navigation-basics). This page goes one step deeper and shows how to organize the sidebar as your documentation grows.

## Open the side navigation file

The side navigation lives here:

```text
config/navigation/sidenav.yaml
```

The starter project uses a small example:

```yaml
- label: The Ring
  expanded: true
  children:
    - label: Lore of the Ring
      path: /lore
    - label: Wielding the Ring
      path: /wielding-the-ring
    - label: Safeguards
      path: /safeguards
```

This file is written in YAML. Spaces matter, so keep the indentation lined up.

## Add a simple link

A sidebar link needs a `label` and a `path`:

```yaml
- label: Installation
  path: /installation
```

The `label` is what readers see.

The `path` is the route the link opens. Use the browser route, not the `.md` file path.

## Group related links

Most documentation sites use groups:

```yaml
- label: Getting Started
  children:
    - label: Installation
      path: /getting-started/installation
    - label: First Project
      path: /getting-started/first-project
```

The group label helps readers understand what the links have in common.

Use groups when you have several pages that belong together.

## Link the group label

A group can also link to a page.

This is useful when the group has an overview page and several detail pages:

```yaml
- label: Getting Started
  path: /getting-started
  children:
    - label: Installation
      path: /getting-started/installation
    - label: First Project
      path: /getting-started/first-project
```

In this example, clicking `Getting Started` opens `/getting-started`.

The child links still appear under the group.

## Open a group by default

Add `expanded: true` when you want a group to start open:

```yaml
- label: Getting Started
  expanded: true
  children:
    - label: Installation
      path: /getting-started/installation
    - label: First Project
      path: /getting-started/first-project
```

This is helpful for the first section readers are likely to use or you do not have many pages and you want all the groups to be expanded by default.


## Keep labels short

Use labels that are clear at a glance:

```yaml
- label: Site Configuration
  path: /configuration/site-configuration
```

Avoid labels that try to explain the whole page:

```yaml
- label: How to Configure the Main Site Settings
  path: /configuration/site-configuration
```

The page title can be longer. The sidebar label should stay easy to scan.

## Match links to real pages

If you create this file:

```text
content/en/configuration/site-configuration.md
```

Use this route in navigation:

```yaml
- label: Site Configuration
  path: /configuration/site-configuration
```

Do not link to the Markdown file:

```yaml
- label: Site Configuration
  path: /configuration/site-configuration.md
```

Readers use routes, so navigation should use routes too.

## Save and check the sidebar

Save `config/navigation/sidenav.yaml`.

If your local server is running, the sidebar should update automatically. Click each new link once to make sure it opens the page you expected.

## Next step

[Configure top navigation](/configuration/top-navigation).
