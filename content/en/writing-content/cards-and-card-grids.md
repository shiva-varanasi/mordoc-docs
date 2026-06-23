---
title: Cards and Card Grids
description: Create visual groups of links with cards and card grids.
---

Cards are useful when you want to guide readers toward a few related pages or choices.

A card is a small content block. A card grid arranges multiple cards together.

## Use cards for choices

Use cards when a reader needs to choose where to go next.

For example, a homepage might link to the most important sections:

```markdown
{% cardGrid cols="3" %}
{% card title="Getting Started" path="/getting-started/create-project" %}
Create your first Mordoc project.
{% /card %}

{% card title="Writing Content" path="/writing-content/markdown-basics" %}
Learn how to write pages.
{% /card %}

{% card title="Configuration" path="/configuration/site-configuration" %}
Customize your documentation site.
{% /card %}
{% /cardGrid %}
```

## Add a card grid

Start with a `cardGrid`:

```markdown
{% cardGrid cols="3" %}
{% /cardGrid %}
```

The `cols` value controls how many columns the grid tries to show on wide screens. Common values are `2` and `3`.

Mordoc will still adapt the layout on smaller screens.

## Add cards inside the grid

Each card needs a `title`:

```markdown
{% cardGrid cols="2" %}
{% card title="Install" path="/guides/install" %}
Install the product and check that it runs.
{% /card %}

{% card title="Configure" path="/guides/configure" %}
Adjust settings for your project.
{% /card %}
{% /cardGrid %}
```

Use `path` when the card should link somewhere.

The `title` field is required. The other card fields are optional.

## Add icons or images

You can add an icon:

```markdown
{% card title="Security" path="/security" icon="/images/icons/shield.svg" %}
Review security recommendations.
{% /card %}
```

You can also add an image:

```markdown
{% card title="Release Notes" path="/releases" image="/images/releases.png" %}
See what changed in the latest version.
{% /card %}
```

Files used for `icon` and `image` belong in `public/`.

## Add a small tag

Use `tag` for short labels like `New`, `Start here`, or `Recommended`.

```markdown
{% card title="Quickstart" path="/quickstart" tag="Start here" %}
Begin with the fastest path through the docs.
{% /card %}
```

Use tags sparingly. If every card has a tag, the tags stop feeling helpful.

## Card options

Cards support these fields:

* `title` is required and becomes the card heading.
* `path` makes the card link to another page or website.
* `icon` shows a small icon.
* `image` shows a larger image.
* `tag` shows a short label such as `New` or `Start here`.

Use only the fields that help readers choose where to go next.

Card grids support `cols`, which controls the preferred number of columns on wide screens.

## Keep card text short

Card text should help readers choose. One short sentence is usually enough.

## Next step

* [Create landing pages](/writing-content/landing-pages).
