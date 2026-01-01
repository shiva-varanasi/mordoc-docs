---
title: Search
description: Learn about the automatically generated search functionality powered by Pagefind in Mordoc.
---

Mordoc provides automatic client-side search functionality powered by [Pagefind](https://pagefind.app/). Search is generated during the build process with no configuration required.

# How search works

Search functionality is completely automatic in Mordoc:

1. **Build Time Generation**: Search index is created during `npm run build`
2. **Client-Side Only**: Search runs entirely in the browser, no backend needed
3. **Zero Configuration**: No setup or configuration files required
4. **Fast & Lightweight**: Optimized for performance with minimal bundle size

# Styling searchbar

Mordoc provides sensible default styles for searchbar. If you want to make subtle changes to searchbar colors to better match your brand, you can do so by adding a `header.json` file under the `config/styles/` directory.

This file allows you to control how searchbar appears in both light and dark modes.

## Available style variables

{% table %}
* Variable
* Description
* Example HEX value
---
* `searchHoverBorderColor`
* Searchbar border color on hover in light mode
* `#171717`
---
* `searchHoverBorderColorDark`
* Searchbar border color on hover in dark mode
* `#fafafa`
---
{% /table %}

## Example configurations

**Blue borders:**

```json
{
  "searchHoverBorderColor": "#0665c4",
  "searchHoverBorderColorDark": "#61b1f2"
}
```

**Green links:**

```json
{
  "searchHoverBorderColor": "#059669",
  "searchHoverBorderColorDark": "#10b981"
}
```