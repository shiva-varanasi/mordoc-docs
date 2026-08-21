# Mordoc Content Syntax Reference

This file describes the Mordoc-specific syntax used in content files. Read this when writing, editing, or discussing English content.

For rules on translating content into other languages, see `TRANSLATE.md` instead — that file covers what to translate/preserve and references this one for tag mechanics.

## Frontmatter

Every page starts with a YAML frontmatter block between `---` delimiters.

```markdown
---
title: My Page Title
description: A short description of the page.
layout: landing
---
```

**Fields:**
- `title` — required on every page.
- `description` — optional.
- `layout: landing` — optional flag marking a landing page.

## Variables

Variables are defined in `config/variables.yaml` and referenced in content with double curly braces.

**In body text:**
```markdown
Welcome to {% $productName %}.
```

**In link tags:**
```markdown
{% link path=$SUPPORT_PORTAL_URL %}Contact support{% /link %}
```

**In image tags:**
```markdown
{% image src=$IMAGE_LINK alt="Artwork" /%}
```

## Tags (Markdoc Components)

Mordoc uses Markdoc-style tags: `{% tagName attr="value" %}` ... `{% /tagName %}`.

---

### Callout

Highlights important messages. `type` is one of `note`, `tip`, `warning`, `danger`.

```markdown
{% callout type="note" title="Good to know" %}
Body text here.
{% /callout %}
```

**Attributes:** `type` (keyword: `note`/`tip`/`warning`/`danger`), `title` (text).

---

### Table

Mordoc's custom table syntax (different from standard Markdown tables).

```markdown
{% table %}
* Header 1
* Header 2
---
* Row 1, Cell 1
* Row 1, Cell 2
---
* Row 2, Cell 1
* Row 2, Cell 2
---
{% /table %}
```

Each `*` is a cell; `---` separates rows. Cells can contain nested content (callouts, code blocks, lists, images).

---

### Card and Card Grid

```markdown
{% cardGrid cols="3" %}
{% card title="Getting Started" path="/getting-started/create-project" icon="/icons/start.svg" tag="Start here" %}
Card body text here.
{% /card %}
{% /cardGrid %}
```

**`cardGrid` attributes:** `cols` (number of columns).
**`card` attributes:** `title` (text), `path` (route), `icon` (asset path), `tag` (short text label).

---

### Hero

Used at the top of landing pages.

```markdown
{% hero
  title="My Product Docs"
  titleAccent="made simple"
  description="Find guides and examples."
  background="/images/hero.png"
%}
{% button path="/getting-started" %}
Get started
{% /button %}
{% /hero %}
```

**Attributes:** `title`, `titleAccent`, `description` (text), `image` (asset path, a supporting image shown below the CTAs), `background` (asset path only, never a color). Colors are not attributes: title, title-accent, and description color are all set once in `Hero.module.css`'s tokens (`--hero-title-color`, etc.), not per-instance in Markdown.

---

### Section

Groups content on landing pages.

```markdown
{% section title="Everything you need" background="/images/section-bg.png" %}
Body text here.
{% /section %}
```

**Attributes:** `title` (text), `background` (asset path only, never a color; a solid background color is set once in `Section.module.css`'s `--section-bg` token, not per-instance in Markdown).

---

### Button

```markdown
{% button path="/getting-started" %}
Get started
{% /button %}

{% button path="/learn-more" variant="secondary" %}
Learn more
{% /button %}
```

**Attributes:** `path` (route), `variant` (`primary`/`secondary`).

---

## Diagrams (`sequence-diagram` code blocks)

Fenced blocks tagged `sequence-diagram` hold diagram DSL, not literal code.

```
actor <id> [as "<label>"] [icon=<path>]
<from> -> <to>: <message text>
<from> --> <to>: <message text>
# comment text
```

- `actor <id> as "<label>" icon=<path>` declares a participant.
- `->` is a synchronous message, `-->` a response/async message.
- `\n` inside message text is a line break within the diagram bubble.
- `#` starts a comment.

Example:
```
actor frodo as "Frodo" icon=/icons/frodo.svg
frodo -> gandalf: I will take it,\nthough I do not know the way
```

Note: the default monospace font renders `->` with ligatures as a single arrow glyph — when writing example code elsewhere that shows arrow syntax, consider spelling out the style in words to avoid confusion.

---

## Navigation Files

Depending on the project, navigation files may include:

- `config/navigation/sidenav.yaml` — single site-wide sidebar (used when `topnav.yaml` does **not** exist)
- `config/navigation/topnav.yaml` — optional; when present, replaces `sidenav.yaml` with per-area sidenav files
- `config/navigation/headernav.yaml` — optional header links
- Custom per-area sidenav files referenced from `topnav.yaml` (e.g., `config/navigation/field-manual.yaml`, `config/navigation/ship-systems.yaml`)

When `topnav.yaml` exists there is **no** `sidenav.yaml` — labels live in `topnav.yaml` and all custom sidenav files it references via the `sidenav:` field.

Each navigation entry has a `label` (display text), `path` (route), and may have `variant` or `expanded` flags.

## Languages

`config/language.json` lists every language the site supports (default/source language plus targets). Content for a non-default language `<lang>` lives under `content/<lang>/...`, mirroring the same relative paths as `content/en/`.
