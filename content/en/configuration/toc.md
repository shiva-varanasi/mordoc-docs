---
title: Table of Contents
description: Configure the automatically generated table of contents sidebar for your Mordoc documentation pages.
---

The table of contents (TOC) provides an at-a-glance overview of a page's structure and enables quick navigation to specific sections. Mordoc automatically generates the TOC from your page headings.

# How TOC Works

The TOC is automatically generated from the heading structure of each page. By default, it displays headings level 2 through 6 and shows on the right side of the page.

# Default Behavior

By default, the TOC:

- **Automatically generates** from page headings
- **Displays on the right side** of the page  
- **Highlights current section** as you scroll
- **Sticky positioning** - stays visible while scrolling
- **Hides on small screens** - Shows only on larger displays (1280px+)

{% callout type="note" %}
The TOC is completely automatic. You don't need to manually create or update it—just write headings in your markdown and the TOC is generated.
{% /callout %}

# Styling the TOC

Customize TOC appearance through configuration.

Edit `config/styles/toc.json` (create if it doesn't exist):

```json
{
  "tocLinkActiveColor": "#171717",
  "tocLinkActiveColorDark": "#FAFAFA"
}
```

## Available Style Variables for TOC

| Variable | Description | Default |
|----------|-------------|---------|
| `tocLinkActiveColor` | Active link color (light mode) | Inherits from nav active color |
| `tocLinkActiveColorDark` | Active link color (dark mode) | Inherits from nav active color |

# Next Steps

- [Search Configuration](/configuration/search) - Set up search functionality
- [Branding](/configuration/branding) - Customize logo and colors
- [Side Navigation](/configuration/sidenav) - Configure main navigation