---
title: Write Pages
description: Make your first content edit in a Mordoc page.
---

Now that you have seen the project structure, it is time to change a page.

You do not need to learn all of Mordoc's writing syntax yet. Start with one small edit, then preview it in the browser.

## Open a sample page

In your project, open this file:

```text
content/en/lore.md
```

This is one of the fictional pages from the starter template.

## Change a sentence

Find a sentence in the page body and change it to something simple.

For example, you might replace some starter text with:

```markdown
This is my first Mordoc page edit.
```

Save the file.

If your local server is still running from the previous step, the browser preview should update automatically. If the server is not running, start it again:

```bash
npm run dev
```

## Notice the page parts

A Mordoc page has two main parts:

```markdown
---
title: Lore of the Ring
description: A short history of the One Ring and the forces bound to it.
---

This is the page body.

## Before you begin

This is a section inside the page.
```

The part between the `---` lines is called frontmatter. It gives Mordoc information about the page.

The writing below the frontmatter is the page body. This is where your paragraphs, lists, links, images, callouts, cards, and other content go.

The [Writing Content](/writing-content/markdown-basics) section will explain the writing syntax in detail later.

## The title field

Every page needs a `title` in its frontmatter:

```yaml
title: Lore of the Ring
```

Mordoc uses this as the main page heading. Because the title already becomes the main heading, start headings in the page body with `##`, not `#`.

For example:

```markdown
## Before you begin

Write your section content here.
```

## The description field

The `description` field is optional, but it is a good habit to include it:

```yaml
description: A short history of the One Ring and the forces bound to it.
```

Use one short sentence that explains what the page is about. Mordoc can use it for page information and search engine previews.

The [Frontmatter Reference](/reference/frontmatter) page will list all supported frontmatter fields later.

## Create a new page

After you are comfortable editing an existing page, create a new Markdown file:

```text
content/en/my-first-page.md
```

Add this content:

```markdown
---
title: My First Page
description: A simple test page for learning Mordoc.
---

This is my first new page.

## What I am learning

I am learning how Mordoc turns Markdown files into documentation pages.
```

This creates a page at:

```text
/my-first-page
```

You will learn how file paths become page URLs in the next step.

{% callout type="note" title="Why you may not see it in the sidebar yet" %}
Creating the file creates the page route, but it does not automatically add the page to the sidebar. Navigation is controlled separately so you can choose which pages appear in the menu.
{% /callout %}

## Next step

[Learn how routes and links work](/getting-started/routes-and-links).
