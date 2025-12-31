---
title: Links
description: Create hyperlinks, cross-references, and external links in your documentation.
---

Links connect your documentation pages together and point to external resources. Mordoc supports standard markdown link syntax with automatic handling of external links.

# Syntax

Create links using markdown bracket notation:

```markdown
[Link Text](URL)
```

## Example

{% table %}
* Syntax
* Result
---
* 
  ```markdown
  [Mordoc docs](https://mordoc.dev)
  ```
* [Mordoc docs](https://mordoc.dev)
---
{% /table %}

# Link types

## External links

Link to websites outside your documentation:

{% table %}
* Syntax
* Result
---
* 
  ```markdown
  [Node.js Official Site](https://nodejs.org)
  [GitHub](https://github.com)
  ```
* [Node.js Official Site](https://nodejs.org)

  [GitHub](https://github.com)
---
{% /table %}

## Internal links

Link to other pages within your documentation using paths:

{% table %}
* Syntax
* Result
---
* 
  ```markdown
  [Create your first project](/get-started/creating-project)
  [Install Git](/prerequisites/git)
  ```
* [Create your first project](/get-started/creating-project)

  [Install Git](/prerequisites/git)
---
{% /table %}

## Email links

Create mailto links:

{% table %}
* Syntax
* Result
---
* 
  ```markdown
  [Contact Support](mailto:support@example.com)
  ```
* [Contact Support](mailto:support@example.com)
---
{% /table %}

# Styling links

Mordoc provides sensible default styles for links. If you want to customize link colors to better match your brand, you can do so by adding a `typography.json` file under the `config/styles/` directory.

This file allows you to control how links appear in both light and dark modes.

## Available style variables

{% table %}
* Variable
* Description
* Example HEX value
---
* `linkColor`
* Link color in light mode
* `#171717`
---
* `linkColorDark`
* Link color in dark mode
* `#fafafa`
---
* `linkHoverColor`
* Link color on hover in light mode
* `#000000`
---
* `linkHoverColorDark`
* Link color on hover in dark mode
* `#FFFFFF`
---
{% /table %}

## Example configurations

**Blue links:**

```json
{
  "linkColor": "#0665c4",
  "linkColorDark": "#61b1f2",
  "linkHoverColor": "#0a0b66",
  "linkHoverColorDark": "#93c5fd"
}
```

**Green links:**

```json
{
  "linkColor": "#059669",
  "linkColorDark": "#10b981",
  "linkHoverColor": "#047857",
  "linkHoverColorDark": "#34d399"
}
```

# Next steps

* [Images](/syntax-components/images) - Embed images in your documentation
* [Lists](/syntax-components/lists) - Create ordered and unordered lists
* [Code Blocks](/syntax-components/code-blocks) - Add syntax-highlighted code examples
