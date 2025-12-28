---
title: Links
description: Create hyperlinks, cross-references, and external links in your Mordoc documentation with markdown syntax.
---

Links connect your documentation pages together and point to external resources. Mordoc supports standard markdown link syntax with automatic handling of external links.

## Basic Link Syntax

Create links using markdown bracket notation:

```markdown
[Link Text](URL)
```

### Example

```markdown
[Visit our website](https://example.com)
```

Result: [Visit our website](https://example.com)

## Link Types

### External Links

Link to websites outside your documentation:

```markdown
[Node.js Official Site](https://nodejs.org)
[GitHub](https://github.com)
```

External links:
- [Node.js Official Site](https://nodejs.org)
- [GitHub](https://github.com)

{% callout type="note" %}
External links automatically open in a new tab. This is hardcoded behavior and cannot be changed.
{% /callout %}

### Internal Links

Link to other pages within your documentation using paths:

```markdown
[Getting Started](/get-started/creating-project)
[Configuration Guide](/configuration/sidenav)
```

Internal links:
- [Getting Started](/get-started/creating-project)
- [Configuration Guide](/configuration/sidenav)

#### Internal Link Path Rules

- Start with `/` for absolute paths from site root
- Match the file path without the `.md` extension
- Use lowercase and hyphens

{% table %}
* File Path
* Link Path
---
* `content/en/guides/intro.md`
* `/guides/intro`
---
* `content/en/api/reference.md`
* `/api/reference`
---
* `content/en/index.md`
* `/`
{% /table %}

### Anchor Links

Link to specific sections within a page using heading IDs:

```markdown
[Jump to Installation](#installation)
[See Prerequisites](/get-started/creating-project#prerequisites)
```

Anchor links:
- [Jump to Link Types](#link-types)
- [Jump to Styling](#styling-links)

Heading IDs are automatically generated from heading text:
- Converted to lowercase
- Spaces become hyphens
- Special characters removed

### Email Links

Create mailto links:

```markdown
[Contact Support](mailto:support@example.com)
```

Result: [Contact Support](mailto:support@example.com)

## Styling Links

Customize link colors through the typography configuration file.

Edit `config/styles/typography.json`:

```json
{
  "linkColor": "#0665c4",
  "linkColorDark": "#0665c4",
  "linkHoverColor": "#0a0b66",
  "linkHoverColorDark": "#61b1f2"
}
```

### Available Style Variables

{% table %}
* Variable
* Description
* Default
---
* `linkColor`
* Link color (light mode)
* `#171717`
---
* `linkColorDark`
* Link color (dark mode)
* `#fafafa`
---
* `linkHoverColor`
* Link hover color (light mode)
* `#000000`
---
* `linkHoverColorDark`
* Link hover color (dark mode)
* `#FFFFFF`
{% /table %}

{% callout type="note" %}
These are the ONLY customizable properties for links. Other aspects (underlines, font weight, transitions) are controlled by the design system to ensure consistency.
{% /callout %}

### Example Configurations

**Blue Links:**

```json
{
  "linkColor": "#0665c4",
  "linkColorDark": "#61b1f2",
  "linkHoverColor": "#0a0b66",
  "linkHoverColorDark": "#93c5fd"
}
```

**Subtle Links:**

```json
{
  "linkColor": "#525252",
  "linkColorDark": "#b3b3b3",
  "linkHoverColor": "#171717",
  "linkHoverColorDark": "#fafafa"
}
```

**Green Links:**

```json
{
  "linkColor": "#059669",
  "linkColorDark": "#10b981",
  "linkHoverColor": "#047857",
  "linkHoverColorDark": "#34d399"
}
```

## Next Steps

- [Images](/syntax-components/images) - Embed images in your documentation
- [Lists](/syntax-components/lists) - Create ordered and unordered lists
- [Code Blocks](/syntax-components/code-blocks) - Add syntax-highlighted code examples
