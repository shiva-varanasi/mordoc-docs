---
title: Table of Contents
description: Configure the automatically generated table of contents sidebar for your documentation pages.
---

The table of contents (TOC) provides an at-a-glance overview of a page's structure and enables quick navigation to specific sections.

# How TOC Works

The TOC is automatically generated from the heading structure of each page and is shown on the right side of the page.

# Default Behavior

By default, the TOC:

* **Highlights current section** as you scroll
* **Sticky positioning** - stays visible while scrolling
* **Hides on small screens** - Shows only on larger displays

# Styling the TOC

If you want to customize TOC colors to better match your brand, you can do so by adding a `toc.json` file under the `config/styles/` directory.

This file allows you to control how TOC active items appear in both light and dark modes.

```json
{
  "tocLinkActiveColor": "#E5E5E5",
  "tocLinkActiveColorDark": "#1F1F1F"
}
```

## Available Style Variables

{% table %}
* Variable
* Description
* Example HEX value
---
* `tocLinkActiveColor`
* Text color of active item of TOC in light mode
* `#171717`
---
* `tocLinkActiveColorDark`
* Text color of active item of TOC in dark mode
* `#FAFAFA`
---
{% /table %}

