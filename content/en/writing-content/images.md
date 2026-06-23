---
title: Images
description: Add images, including ones with a variable-driven source.
---

Put content images in `public/`, then reference them with a path that starts with `/`.

## Basic images

```markdown
![A short description of the image](/images/my-image.png)
```

The text in brackets is the image's `alt` text — keep it descriptive, since it is read by screen readers and shown if the image fails to load.

The [Images and Files](/getting-started/images-and-files) page shows this step by step.

## Images with variables

Like links, a plain Markdown image's source is parsed as plain text, so a variable inside it is never resolved:

```markdown
![Artwork]($IMAGE_LINK)
```

This renders the literal text `$IMAGE_LINK` as the image source, not the value from `config/variables.yaml`.

When an image source needs to come from a variable, use the `image` tag instead. It is self-closing, since `alt` is an attribute rather than image content:

```markdown
{% image src=$IMAGE_LINK alt="Artwork" /%}
```

`src` resolves against `config/variables.yaml` the same way `{% $variableName %}` does in running text. See [Variables](/configuration/variables) to learn how to define one.

Use the tag form only when the source actually needs to vary — for ordinary static images, plain Markdown is simpler and works the same way.

## Next step

[Use callouts](/writing-content/callouts).
