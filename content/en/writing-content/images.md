---
title: Images
description: Add images and icons, including ones with a variable-driven source.
---

Put content images in `public/`, then reference them with a path that starts with `/`.

## Basic images

```markdown
![Artwork](/images/content-images/artwork.png)
```

The text in brackets is the image's `alt` text. Keep it descriptive, since it is read by screen readers and shown if the image fails to load.

**Here is how it renders**

![Artwork](/images/content-images/artwork.png)

The [Images and Files](/getting-started/images-and-files) page walks through adding an image step by step.

## Icons

Icons work the same way as any other image: place the file in `public/`, then reference its path.

```text
public/icons/shield.svg
```

Small SVGs are the most common choice, since they stay sharp at any size.

You won't insert an icon into page text directly. Instead, certain components take an icon file through an attribute, such as `icon` on a [card](/writing-content/cards-and-card-grids) or an actor's icon in a [sequence diagram](/creating-diagrams/sequence-diagrams).

## Images with variables

Sometimes an image's source should come from a reusable value instead of being written directly, for example a logo URL that might change later. See [Variables](/configuration/variables) for how to define a variable and use it in an image.

## Next step

- [Add clips](/writing-content/clip).
