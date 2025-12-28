---
title: Search
description: Learn about the automatically generated search functionality powered by Pagefind in Mordoc.
---

Mordoc provides automatic client-side search functionality powered by **Pagefind**. Search is generated during the build process with no configuration required.

# How Search Works

Search functionality is completely automatic in Mordoc:

1. **Build Time Generation**: Search index is created during `npm run build`
2. **Client-Side Only**: Search runs entirely in the browser, no backend needed
3. **Zero Configuration**: No setup or configuration files required
4. **Fast & Lightweight**: Optimized for performance with minimal bundle size

{% callout type="note" %}
Mordoc uses Pagefind for search, which creates a lightweight, static search index during the build process. This provides instant search without servers or external services.
{% /callout %}

# Using Search

## Accessing Search

The search bar appears automatically in the site header:

- **Desktop**: Top navigation bar
- **Mobile**: Accessible via hamburger menu

## Keyboard Shortcuts

{% table %}
* Shortcut
* Action
---
* `/`
* Open search
---
* `Esc`
* Close search
---
* `↑` / `↓`
* Navigate results
---
* `Enter`
* Go to selected result
{% /table %}

## Search Features

Pagefind automatically searches:

- **Page titles** - Highest relevance weight
- **Headings** - High relevance weight
- **Body content** - Standard relevance weight
- **Custom frontmatter** - Included in search

# Search Capabilities

## Full-Text Search

Search queries work across all content:

```
installation
```

Finds all pages containing "installation".

## Multi-Word Search

Multiple words are treated as an AND query:

```
api authentication
```

Finds pages containing both "api" AND "authentication".

## Phrase Search

Use quotes for exact phrases:

```
"getting started"
```

Finds the exact phrase "getting started".

# What Gets Indexed

By default, Pagefind indexes:

- ✅ All markdown content
- ✅ Page titles and headings
- ✅ Paragraph text
- ✅ List items
- ❌ Code blocks (excluded by default)
- ❌ Navigation menus
- ❌ Headers and footers

{% callout type="note" %}
Pagefind automatically excludes navigation, headers, and other non-content elements from the search index.
{% /callout %}

# Updating Search Index

The search index is generated at build time. To update search results:

```bash
npm run build
```

Changes to content files require a rebuild for search to reflect updates.

# Next Steps

- [Branding](/configuration/branding) - Customize your site's appearance
- [Build](/deployment/build) - Build your site with search enabled
- [Preview](/deployment/preview) - Test search locally before deploying
