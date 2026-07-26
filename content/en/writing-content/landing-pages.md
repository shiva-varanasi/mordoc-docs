---
title: Landing Pages
description: Create full-width pages for homepages and overview pages.
---

Most Mordoc pages use the normal documentation layout: sidebar on the left, page content in the middle, and a table of contents on the right.

Sometimes you need a different kind of page. A homepage or product overview often works better as a landing page.

## What a landing page changes

A landing page is full-width.

It does not show:

* The side navigation
* The right-side table of contents
* The normal article header

That makes it useful for pages that introduce the site, show cards, or guide readers into the main documentation.

## Turn a page into a landing page

Add `layout: landing` to the page frontmatter:

```markdown
---
title: Home
description: Welcome to my documentation.
layout: landing
---
```

Use landing pages sparingly. Most documentation pages should use the normal layout.

## Add a hero

A hero is a large opening section, usually used at the top of a landing page.

```markdown
{% hero
  title="My Product Docs"
  titleAccent="made simple"
  description="Find guides, reference material, and practical examples."
  background="#120b08"
%}
{% button path="/getting-started/create-project" %}
Get started
{% /button %}
{% /hero %}
```

The `title` is required. Other fields are optional.

A hero can use:

* `title` for the main text
* `titleAccent` for highlighted title text
* `description` for supporting text
* `image` for a hero image
* `background` for a color or image path
* `titleColor`, `titleAccentColor`, and `descriptionColor` for text colors

## Add sections

Use sections to group landing page content:

```markdown
{% section title="Choose where to begin" background="subtle" %}
This section introduces the main paths through the documentation.
{% /section %}
```

The `background` value can be `subtle`, a color, or an image path.

The `title` value is optional on sections, but it is usually helpful.

## Add cards to a landing page

Landing pages often use cards to guide readers:

```markdown
{% section title="Explore the docs" %}
{% cardGrid cols="3" %}
{% card title="Getting Started" path="/getting-started/create-project" tag="Start here" %}
Create and run your first project.
{% /card %}

{% card title="Writing Content" path="/writing-content/markdown-basics" %}
Learn the writing basics.
{% /card %}

{% card title="Configuration" path="/configuration/site-configuration" %}
Customize your site settings.
{% /card %}
{% /cardGrid %}
{% /section %}
```

## Add buttons

Buttons are useful for important calls to action:

```markdown
{% button path="/getting-started/create-project" %}
Create a project
{% /button %}
```

Use `variant="secondary"` for a quieter button:

```markdown
{% button path="/writing-content/markdown-basics" variant="secondary" %}
Learn Markdown
{% /button %}
```

The `path` value is required for buttons. The `variant` value is optional and can be `primary` or `secondary`.

## When to use a landing page

Use a landing page for:

* The homepage
* A product overview
* A major section overview

Use a normal page for:

* Step-by-step guides
* Reference pages
* Troubleshooting pages
* Detailed explanations

## Next step

* [Create diagrams](/creating-diagrams/overview).
