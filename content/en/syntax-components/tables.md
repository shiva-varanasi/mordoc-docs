---
title: Tables
description: Create rich, structured tables in your Mordoc documentation using Markdoc table syntax.
---

Tables organize structured data into rows and columns, making information easy to scan and compare. Mordoc uses Markdoc's table syntax which supports rich content within cells.

## Markdoc Table Syntax

Mordoc supports both standard Markdown table syntax (with pipes `|`) and Markdoc's custom table tag syntax. The Markdoc syntax is recommended for tables with rich content.

### Basic Markdoc Table

```
{% table %}
* Header 1
* Header 2
* Header 3
---
* Row 1, Cell 1
* Row 1, Cell 2
* Row 1, Cell 3
---
* Row 2, Cell 1
* Row 2, Cell 2
* Row 2, Cell 3
{% /table %}
```

Result:

{% table %}
* Header 1
* Header 2
* Header 3
---
* Row 1, Cell 1
* Row 1, Cell 2
* Row 1, Cell 3
---
* Row 2, Cell 1
* Row 2, Cell 2
* Row 2, Cell 3
{% /table %}

### How It Works

- First section (before first `---`) defines headers using `*` (asterisk)
- Each subsequent section (separated by `---`) defines a row
- Each `*` item within a row section is a cell
- Rich markdown content is supported within cells

## Standard Markdown Tables

You can also use standard markdown pipe syntax:

```markdown
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Row 1    | Data     | Data     |
| Row 2    | Data     | Data     |
```

Result:

| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Row 1    | Data     | Data     |
| Row 2    | Data     | Data     |

## Rich Content in Tables

The Markdoc table syntax supports rich content within cells:

### Links in Tables

```
{% table %}
* Resource
* Link
---
* Documentation
* [Read docs](/get-started/creating-project)
---
* GitHub
* [View source](https://github.com)
{% /table %}
```

{% table %}
* Resource
* Link
---
* Documentation
* [Read docs](/get-started/creating-project)
---
* GitHub
* [View source](https://github.com)
{% /table %}

### Code in Tables

```
{% table %}
* Command
* Description
---
* `npm install`
* Install dependencies
---
* `npm run dev`
* Start development server
---
* `npm run build`
* Build for production
{% /table %}
```

{% table %}
* Command
* Description
---
* `npm install`
* Install dependencies
---
* `npm run dev`
* Start development server
---
* `npm run build`
* Build for production
{% /table %}

### Emphasis in Tables

```
{% table %}
* Feature
* Status
* Notes
---
* **Bold text**
* *Italic text*
* `Code text`
---
* Normal text
* ~~Strikethrough~~
* Regular
{% /table %}
```

{% table %}
* Feature
* Status
* Notes
---
* **Bold text**
* *Italic text*
* `Code text`
---
* Normal text
* ~~Strikethrough~~
* Regular
{% /table %}

## Common Table Patterns

### API Parameter Documentation

```
{% table %}
* Parameter
* Type
* Required
* Description
---
* `name`
* string
* ✓
* Project name
---
* `version`
* string
* ✓
* Version number
---
* `description`
* string
* ✗
* Project description
{% /table %}
```

{% table %}
* Parameter
* Type
* Required
* Description
---
* `name`
* string
* ✓
* Project name
---
* `version`
* string
* ✓
* Version number
---
* `description`
* string
* ✗
* Project description
{% /table %}

### Configuration Options

```
{% table %}
* Option
* Type
* Default
* Description
---
* `port`
* number
* `3000`
* Development server port
---
* `theme`
* string
* `"light"`
* Default theme mode
---
* `search`
* boolean
* `true`
* Enable search feature
{% /table %}
```

{% table %}
* Option
* Type
* Default
* Description
---
* `port`
* number
* `3000`
* Development server port
---
* `theme`
* string
* `"light"`
* Default theme mode
---
* `search`
* boolean
* `true`
* Enable search feature
{% /table %}

### Comparison Tables

```
{% table %}
* Feature
* Mordoc
* Alternative A
* Alternative B
---
* Open Source
* ✓
* ✓
* ✗
---
* Self-Hosted
* ✓
* ✗
* ✗
---
* Custom Themes
* ✓
* Limited
* ✗
---
* Price
* Free
* $99/mo
* $49/mo
{% /table %}
```

{% table %}
* Feature
* Mordoc
* Alternative A
* Alternative B
---
* Open Source
* ✓
* ✓
* ✗
---
* Self-Hosted
* ✓
* ✗
* ✗
---
* Custom Themes
* ✓
* Limited
* ✗
---
* Price
* Free
* $99/mo
* $49/mo
{% /table %}

### Browser Compatibility

```
{% table %}
* Browser
* Minimum Version
* Recommended
* Notes
---
* Chrome
* 90+
* Latest
* Full support
---
* Firefox
* 88+
* Latest
* Full support
---
* Safari
* 14+
* Latest
* Limited CSS Grid
---
* Edge
* 90+
* Latest
* Full support
{% /table %}
```

{% table %}
* Browser
* Minimum Version
* Recommended
* Notes
---
* Chrome
* 90+
* Latest
* Full support
---
* Firefox
* 88+
* Latest
* Full support
---
* Safari
* 14+
* Latest
* Limited CSS Grid
---
* Edge
* 90+
* Latest
* Full support
{% /table %}

## Next Steps

- [Code Blocks](/syntax-components/code-blocks) - Add syntax-highlighted code examples
- [Callouts](/syntax-components/callouts) - Create styled alert and info boxes
- [Cards](/syntax-components/cards) - Build card layouts and grids