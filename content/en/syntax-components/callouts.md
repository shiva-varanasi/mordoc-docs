---
title: Callouts
description: Create styled callout boxes for notes, warnings, and critical information in your documentation.
---

Callouts draw attention to important information by displaying content in visually distinct boxes. Mordoc supports three types of callouts: note, warning, and danger.

# Syntax

Create callouts using syntax:

```markdown
{% callout type="note" title="Note" %}
Even the smallest person can change the course of the future.
{% /callout %}
```

# Callout types

## Note callouts

Use notes for helpful tips, additional context, or supplementary information:

{% table %}
* Syntax
* Result
---
* 
  ```markdown
  {% callout type="note" title="Pro tip" %}
  When at the gates of Moria, say *mellon*.
  {% /callout %}
  ```
* 
  {% callout type="note" title="Pro tip" %}
  When at the gates of Moria, say *mellon*.
  {% /callout %}
---
{% /table %}

## Warning callouts

Use warnings for important information that users should be aware of:

{% table %}
* Syntax
* Result
---
* 
  ```markdown
  {% callout type="warning" title="Warning" %}
  Some enemies, like the Balrog beneath the mountain, are not meant to be fought at all
  {% /callout %}
  ```
* 
  {% callout type="warning" title="Warning" %}
  Some enemies, like the Balrog beneath the mountain, are not meant to be fought at all
  {% /callout %}
---
{% /table %}

## Danger callouts

Use danger callouts for critical warnings about destructive or risky actions:

{% table %}
* Syntax
* Result
---
* 
  ```markdown
  {% callout type="danger" title="Danger" %}
  Do not claim the Ring for yourself, or it will claim you in return.
  {% /callout %}
  ```
* 
  {% callout type="danger" title="Danger" %}
  Do not claim the Ring for yourself, or it will claim you in return.
  {% /callout %}
---
{% /table %}

# Callouts without titles

You can also write callouts without titles:

{% table %}
* Syntax
* Result
---
* 
  ```markdown
  {% callout type="note" %}
  Even the smallest person can change the course of the future.
  {% /callout %}

  ```
* 
  {% callout type="note" %}
  Even the smallest person can change the course of the future.
  {% /callout %}

---
{% /table %}

# Next steps

- [Cards & Card Grid](/syntax-components/cards) - Create visual card layouts
