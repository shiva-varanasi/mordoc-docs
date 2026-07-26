---
title: Diagrams
description: Create diagrams directly in Markdown, rendered as crisp vector art that matches your site's theme.
---

Mordoc lets you draw diagrams directly in Markdown, using a plain-text syntax inside a fenced code block. No image export, no separate diagramming tool, no file to keep in sync with the page around it — the diagram lives in the page itself.

## Why not just use Mermaid?

Mermaid and tools like it are excellent, and you may already know their syntax. Mordoc builds its own diagram engine anyway, for a few reasons specific to what a documentation site needs:

* **Diagrams that look like the rest of your site.** Mordoc's diagrams are built from the same design tokens as everything around them, so they automatically match your colors, typography, and light/dark theme — no separate theme to configure or keep in sync.
* **No diagram engine shipped to the browser.** Mordoc parses and lays out the diagram once, at build time, in Node, as a native part of the same pipeline that processes the rest of your content. The page ships only the finished result as inline SVG — a visitor's browser never sees the diagram syntax or a diagram-rendering library at all.
* **It behaves like the rest of your content.** A Mordoc diagram is clickable, opening a zoomable lightbox the same way an image does — not a separate interaction model to learn.

{% callout type="note" title="Build-time, not client-side" %}
Because diagrams are parsed and laid out during the build, a broken diagram fails the build with a clear error — the same way a broken link in your navigation config would — rather than shipping a silently blank box to readers.
{% /callout %}

## What's supported today

Mordoc's diagram support ships its first diagram type in this release: **sequence diagrams**, for showing messages passing between participants over time. See [Sequence Diagrams](/mordoc-docs/sequence-diagrams) for the full syntax.

More diagram types may follow in later releases. Adding one doesn't change how existing diagrams are written — each type is its own fenced-code-block language.

## The general shape

Every diagram is a fenced code block whose language names the diagram type:

````markdown
```sequence-diagram
...diagram syntax goes here...
```
````

Mordoc recognizes the language, parses the block's contents, and replaces it with the rendered diagram — the same way it replaces a ` ```javascript ` block with a syntax-highlighted code sample, just routed to a different renderer.

## Next step

* [Create a sequence diagram](/creating-diagrams/sequence-diagrams).
