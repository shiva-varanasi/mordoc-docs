---
title: Diagrams
description: Create diagrams directly in Markdown, rendered as crisp vector art that matches your site's theme.
---

Mordoc continues the philosophy of content as code to diagrams. You draw diagrams directly in Markdown, using a plain-text syntax inside a fenced code block. There is no image to export, no separate diagramming tool, and no file to keep in sync with the page around it. The diagram lives in the page itself.

That matters most once your site has more than one language. An image-based diagram has to be redrawn and re-exported for every language you support, then kept in sync by hand whenever the source diagram changes. A Mordoc diagram is just text, so translating it works the same way as translating a paragraph: update the labels and messages, and Mordoc builds a fully localized diagram from that text, no design tool involved.

## Why not just use Mermaid?

Mermaid and tools like it are excellent, and you may already know their syntax. Mordoc builds its own diagram engine anyway, for a few reasons specific to what a documentation site needs:

* **Diagrams that look like the rest of your site.** Mordoc's diagrams are built from the same design tokens as everything around them, so they automatically match your colors, typography, and light/dark theme. There is no separate theme to configure or keep in sync.
* **No diagram engine shipped to the browser.** Mordoc parses and lays out the diagram once, at build time, in Node, as a native part of the same pipeline that processes the rest of your content. The page ships only the finished result as inline SVG, so a visitor's browser never sees the diagram syntax or a diagram-rendering library at all.
* **It behaves like the rest of your content.** A Mordoc diagram is clickable, opening a zoomable lightbox the same way an image does, which means there is no separate interaction model to learn.

{% callout type="note" title="Build-time, not client-side" %}
Because diagrams are parsed and laid out during the build, a broken diagram fails the build with a clear error, just as a broken link in your navigation config would. Readers never see a silently blank box instead.
{% /callout %}

## The general shape

Every diagram is a fenced code block whose language names the diagram type:

````markdown
```sequence-diagram
...diagram syntax goes here...
```
````

Mordoc recognizes the language, parses the block's contents, and replaces it with the rendered diagram.

## Next step

* [Create a sequence diagram](/creating-diagrams/sequence-diagrams).
