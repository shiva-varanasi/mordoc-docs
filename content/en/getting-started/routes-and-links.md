---
title: Routes and Links
description: Understand how Mordoc turns content files into URLs and how to link between pages.
---

In the previous step, you created a page file:

```text
content/en/my-first-page.md
```

Mordoc turns that file into a page you can open in the browser:

```text
/my-first-page
```

This browser address is called a route.

## Open your new page

If your local server is still running, open this address in your browser:

```text
http://localhost:5173/my-first-page
```

You should see the page you created.

## How page addresses are created

Mordoc looks at the file location inside `content/en/` and creates the matching page address.

Here are a few examples:

```text
content/en/index.md           -> /
content/en/my-first-page.md   -> /my-first-page
content/en/guides/install.md  -> /guides/install
content/en/guides/index.md    -> /guides
```

The `index.md` filename is special. It becomes the main page for its folder.

For example:

```text
content/en/index.md        -> /
content/en/guides/index.md -> /guides
```

You will use this pattern often when organizing groups of pages.

## Link to another page

When you link from one page to another, link to the page address, not the file name.

For example, to link to the page you created:

```markdown
[Read my first page](/my-first-page)
```

Do not write the link like this:

```markdown
[Read my first page](./my-first-page.md)
```

Readers use page addresses in the browser. Your links should use those same addresses.

## Link to the homepage

The homepage is:

```text
/
```

Link to it like this:

```markdown
[Go home](/)
```

## Keep addresses simple

Use lowercase words and hyphens in filenames.

Good examples:

```text
getting-started.md
install-guide.md
account-settings.md
```

Avoid spaces and special characters in filenames.

## More link options

- [Links](/writing-content/links) page will explain more link examples.

- [Languages](/configuration/languages) page will explain how page addresses work when your site has more than one language.

## Next step

- [Add pages to navigation](/getting-started/navigation-basics).
