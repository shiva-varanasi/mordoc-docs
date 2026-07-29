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

External links work the same way; just use the full URL:

```markdown
[Mordoc on GitHub](https://github.com/shiva-varanasi/mordoc)
```

You don't need to do anything special to tell Mordoc which is which. It looks at the link target itself: a relative path like `/my-first-page` is treated as an internal link and takes readers to the new page instantly, without a full page reload, while a full URL starting with `https://` is treated as external and opens in a new tab.

## Link to a section on the page

To link to a specific heading, add `#` followed by the heading text in lowercase with spaces replaced by hyphens. For example, this links to the "Basic links" heading above:

```markdown
[Jump to Basic links](#basic-links)
```

You can link to a heading on a different page the same way: combine the page address with the `#` anchor. For example, this links to the "How page addresses are created" heading on the Routes and Links page:

```markdown
[How page addresses are created](/getting-started/routes-and-links#how-page-addresses-are-created)
```

## Links with variables

Sometimes a link's destination should come from a reusable value instead of being written directly, for example a support URL that might change later. See [Variables](/configuration/variables) for how to define a variable and use it in a link.

## Next step

* [Add images](/writing-content/images).
