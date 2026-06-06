---
title: Images and Files
description: Learn where to place logos, screenshots, downloads, and other static files.
---

Your documentation will often need images, screenshots, diagrams, or downloadable files.

For content files, the main rule is simple: put them in `public/`, then reference them with a path that starts with `/`.

## Add an image folder

Inside your project, create an `images` folder inside `public/`:

```text
public/
└── images/
```

If the folder already exists, you can use it.

## Add an image file

Copy an image into that folder.

For example:

```text
public/images/my-image.png
```

The file can be a screenshot, diagram, illustration, or any image you want to show in a page.

## Show the image in a page

Open the page you created earlier:

```text
content/en/my-first-page.md
```

Add this Markdown where you want the image to appear:

```markdown
![A short description of the image](/images/my-image.png)
```

Save the file. If your local server is running, the preview should update automatically.

## Why the path starts with /

Files inside `public/` are available from the site root.

That means this file:

```text
public/images/my-image.png
```

Is referenced like this:

```markdown
![A short description of the image](/images/my-image.png)
```

Do not include `public` in the Markdown path.

## Write useful image descriptions

The text inside the square brackets is called alt text:

```markdown
![A short description of the image](/images/my-image.png)
```

Write a short description of what the image shows.

For example:

```markdown
![Settings page with the API token field highlighted](/images/api-token.png)
```

Good alt text helps readers who use screen readers and gives context if an image cannot load.

## What about logos?

The starter project also has this folder:

```text
config/assets/
```

That folder is for site-level images, such as the logo in the header. You do not need to change it yet.

Later, the [Assets and Branding](/configuration/assets-and-branding) page will explain logo and favicon files.

## Next step

[Learn more about writing content](/writing-content/markdown-basics).
