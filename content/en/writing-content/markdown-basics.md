---
title: Markdown Basics
description: Learn the basic Markdown patterns used in Mordoc pages.
---

Markdown is the plain-text format you use to write Mordoc pages. It lets you write readable text first, then add simple marks for headings, lists, links, images, and code examples.

You do not need to learn everything at once. Start with the patterns on this page and come back when you need them.

## Start with frontmatter

Every Mordoc page begins with frontmatter:

```markdown
---
title: My First Page
description: A simple test page for learning Mordoc.
---
```

The `title` is required. Mordoc uses it as the main page heading.

The `description` is optional, but it is a good habit to include it. It helps describe the page in search results and page metadata.

Landing pages can also use `layout: landing`. You will learn about that in [Landing Pages](/writing-content/landing-pages).

## Write paragraphs

Below the frontmatter, write normal text:

```markdown
This is the first paragraph.

This is another paragraph.
```

Leave a blank line between paragraphs.

## Add sections

Because the frontmatter title already becomes the main page heading, start headings in the page body with `##`.

```markdown
## Before you begin

Write the section content here.

## Next steps

Write the next section here.
```

Use headings to break a page into clear sections. Avoid skipping from `##` to `####`; if you need a smaller section inside a section, use `###`.

## Add lists

Use bullet lists when the order does not matter:

```markdown
* Create a project
* Edit a page
* Preview the site
```

Use numbered lists when the order matters:

```markdown
1. Open the project folder.
2. Edit a Markdown file.
3. Save the file.
```

## Add links

Use the page address when linking to another page:

```markdown
[Read my first page](/my-first-page)
```

Do not link to the Markdown file itself:

```markdown
[Read my first page](./my-first-page.md)
```

The [Routes and Links](/getting-started/routes-and-links) page explains why Mordoc links use page addresses.

## Add images

Put content images in `public/`, then reference them with a path that starts with `/`.

```markdown
![A short description of the image](/images/my-image.png)
```

The [Images and Files](/getting-started/images-and-files) page shows this step by step.

## Add code examples

Use backticks for short inline code:

```markdown
Run `npm run dev` to start the local server.
```

Use a fenced code block for longer examples:

````markdown
```javascript
const productName = "Mordoc";
const message = `Welcome to ${productName}`;
console.log(message);
```
````

Add the language name after the opening backticks when you know it. Mordoc uses that to highlight the code.

## Next step

[Use callouts](/writing-content/callouts).
