---
title: Links
description: Link to other pages, external sites, and variable-driven targets.
---

Links point a reader to another page in your site, an external site, or an anchor within the current page.

## Basic links

Use the page address when linking to another page:

```markdown
[Read my first page](/my-first-page)
```

Do not link to the Markdown file itself:

```markdown
[Read my first page](./my-first-page.md)
```

The [Routes and Links](/getting-started/routes-and-links) page explains why Mordoc links use page addresses.

External links work the same way — just use the full URL:

```markdown
[Mordoc on GitHub](https://github.com/shiva-varanasi/mordoc)
```

## Links with variables

A plain Markdown link's destination is parsed as plain text, so a variable inside it is never resolved:

```markdown
[Contact support]($SUPPORT_PORTAL_URL)
```

This renders the literal text `$SUPPORT_PORTAL_URL`, not the value from `config/variables.yaml`.

When a link target needs to come from a variable, use the `link` tag instead:

```markdown
{% link path=$SUPPORT_PORTAL_URL %}Contact support{% /link %}
```

`path` resolves against `config/variables.yaml` the same way `{% $variableName %}` does in running text. See [Variables](/configuration/variables) to learn how to define one.

Use the tag form only when the target actually needs to vary — for ordinary internal and external links, plain Markdown links are simpler and work the same way.

## Next step

* [Add images](/writing-content/images).
