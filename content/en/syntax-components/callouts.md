---
title: Callouts
description: Create styled callout boxes for notes, warnings, and critical information in your Mordoc documentation.
---

Callouts draw attention to important information by displaying content in visually distinct boxes. Mordoc supports three types of callouts: note, warning, and danger.

# Basic Callout Syntax

Create callouts using Markdoc tag syntax:

```markdown
{% callout type="note" %}
This is important information for readers.
{% /callout %}
```

# Callout Types

## Note Callouts

Use notes for helpful tips, additional context, or supplementary information:

```markdown
{% callout type="note" %}
This feature is available in all versions of Mordoc.
{% /callout %}
```

Result:

{% callout type="note" %}
This feature is available in all versions of Mordoc.
{% /callout %}

**When to use notes:**
- Helpful tips and best practices
- Additional context or background
- Related information
- Feature availability
- Pro tips

## Warning Callouts

Use warnings for important information that users should be aware of:

```markdown
{% callout type="warning" %}
This operation cannot be undone. Make sure to backup your data first.
{% /callout %}
```

Result:

{% callout type="warning" %}
This operation cannot be undone. Make sure to backup your data first.
{% /callout %}

**When to use warnings:**
- Potential issues or pitfalls
- Important prerequisites
- Breaking changes
- Deprecated features
- Actions that need caution

## Danger Callouts

Use danger callouts for critical warnings about destructive or risky actions:

```markdown
{% callout type="danger" %}
Running this command will permanently delete all your data. There is no way to recover it.
{% /callout %}
```

Result:

{% callout type="danger" %}
Running this command will permanently delete all your data. There is no way to recover it.
{% /callout %}

**When to use danger:**
- Destructive operations
- Security risks
- Critical errors
- Data loss warnings
- System-breaking actions

# Callouts with Titles

Add custom titles to make callouts more specific:

```markdown
{% callout type="note" title="Pro Tip" %}
You can use keyboard shortcuts to speed up your workflow.
{% /callout %}
```

Result:

{% callout type="note" title="Pro Tip" %}
You can use keyboard shortcuts to speed up your workflow.
{% /callout %}

# Examples with Different Types

```markdown
{% callout type="warning" title="Breaking Change" %}
Version 2.0 removes support for Node.js 14. Please upgrade to Node.js 18 or higher.
{% /callout %}
```

{% callout type="warning" title="Breaking Change" %}
Version 2.0 removes support for Node.js 14. Please upgrade to Node.js 18 or higher.
{% /callout %}

```markdown
{% callout type="danger" title="Security Warning" %}
Never commit your API keys or secrets to version control.
{% /callout %}
```

{% callout type="danger" title="Security Warning" %}
Never commit your API keys or secrets to version control.
{% /callout %}

# Next Steps

- [Cards & Card Grid](/syntax-components/cards) - Create visual card layouts
- [Tables](/syntax-components/tables) - Display tabular data
- [Code Blocks](/syntax-components/code-blocks) - Add syntax-highlighted code
