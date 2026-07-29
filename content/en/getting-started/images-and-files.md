---
title: Images and Files
description: Learn where to place images, icons and other static files.
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

## What about icons and logos?

Icons follow the same `public/` rule as images. See [Icons](/writing-content/images#icons) for how components like cards and sequence diagrams use them.

The site logo works differently: it lives in `config/assets/` instead of `public/`, since it belongs to the site interface rather than a specific page. See [Assets and Branding](/configuration/assets-and-branding) when you are ready to replace it.

## Next step

- [Learn more about writing content](/writing-content/markdown-basics).
