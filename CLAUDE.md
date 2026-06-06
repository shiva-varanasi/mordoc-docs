# Mordoc Content Syntax Reference

This file describes the Mordoc-specific syntax used in content files. When translating content into other languages, preserve all Mordoc syntax exactly as written — only translate the human-readable text.

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
- `title` — required on every page. Translate this value.
- `description` — optional. Translate this value.
- `layout: landing` — optional flag, value is a keyword, do not translate.

## Variables

Variables are defined in `config/variables.yaml` and referenced in content with double curly braces.

**In body text:**
```markdown
Welcome to {{ $productName }}.
```

**In link targets (no curly braces):**
```markdown
[Contact support]($SUPPORT_PORTAL_URL)
```

**Rules for translation:**
- Do not translate `{{ $variableName }}` or `$VARIABLE_NAME` — preserve them verbatim.
- Translate surrounding text as normal.

## Tags (Markdoc Components)

Mordoc uses Markdoc-style tags: `{% tagName attr="value" %}` ... `{% /tagName %}`.

**Rules for translation:**
- Do not translate tag names (`callout`, `card`, `cardGrid`, `hero`, `section`, `button`, `table`).
- Do not translate attribute names (`type`, `title`, `path`, `cols`, `icon`, `image`, `tag`, `variant`, `background`, `titleAccent`, `description`, `titleColor`, `titleAccentColor`, `descriptionColor`).
- Do not translate attribute values that are keywords or paths: `note`, `tip`, `warning`, `danger`, `primary`, `secondary`, `subtle`, `/some/path`, `#hexcolor`.
- **Do translate** attribute values that are human-readable text: `title="..."`, `titleAccent="..."`, `description="..."`, `tag="..."`.
- Do not translate the opening or closing tag syntax itself.

---

### Callout

Highlights important messages. Four types: `note`, `tip`, `warning`, `danger`.

```markdown
{% callout type="note" title="Good to know" %}
Translate the body text here.
{% /callout %}
```

```markdown
{% callout type="warning" title="Check the path" %}
Translate the body text here.
{% /callout %}
```

**What to translate:** `title` attribute value, body text.  
**Do not translate:** `type` attribute value (`note`, `tip`, `warning`, `danger`), tag syntax.

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

**What to translate:** the cell text after each `*`.  
**Do not translate:** `{% table %}`, `{% /table %}`, the `*` list markers, the `---` row separators.

Cells can contain nested content (callouts, code blocks, lists, images). Apply the same translation rules recursively to any nested Mordoc tags inside cells.

---

### Card and Card Grid

```markdown
{% cardGrid cols="3" %}
{% card title="Getting Started" path="/getting-started/create-project" icon="/icons/start.svg" tag="Start here" %}
Translate the card body text here.
{% /card %}
{% /cardGrid %}
```

**What to translate:** `title` attribute value, `tag` attribute value, body text inside `{% card %}...{% /card %}`.  
**Do not translate:** `cols` value, `path` value, `icon` value, `image` value, tag syntax.

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

**What to translate:** `title`, `titleAccent`, `description` attribute values, button body text.  
**Do not translate:** `background` value, `path` value, color values (`titleColor`, `titleAccentColor`, `descriptionColor`), tag syntax.

---

### Section

Groups content on landing pages.

```markdown
{% section title="Everything you need" background="subtle" %}
Translate body text here.
{% /section %}
```

**What to translate:** `title` attribute value, body text.  
**Do not translate:** `background` value (`subtle`, a color, or a path), tag syntax.

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

**What to translate:** button body text.  
**Do not translate:** `path` value, `variant` value (`primary`, `secondary`), tag syntax.

---

## Language-specific Path Prefixes

When translating content for a non-default language folder (e.g., `content/de/`), all relative navigation link paths must be prefixed with the language code.

This applies to:
- Markdown link paths: `[text](/some/page)` → `[text](/de/some/page)`
- `path` attributes in Mordoc tags: `path="/some/page"` → `path="/de/some/page"`

Do **not** prefix asset paths with the language code — images, icons, and backgrounds are shared across all languages:
- `icon="/icons/..."` — leave as-is
- `image="/images/..."` — leave as-is
- `background="/images/..."` — leave as-is

Do **not** prefix paths inside code blocks (fenced with ` ``` `) — preserve them verbatim.

---

## Summary: What to Translate vs. Preserve

| Element | Translate? |
|---|---|
| Frontmatter `title` and `description` values | Yes |
| Frontmatter `layout` value | No |
| `{{ $variableName }}` | No |
| `$VARIABLE_NAME` in link targets | No |
| Tag names (`callout`, `card`, etc.) | No |
| Attribute names (`type`, `path`, `cols`, etc.) | No |
| `type` values (`note`, `tip`, `warning`, `danger`) | No |
| `path`, `icon`, `image`, `background` values | No |
| `variant` values (`primary`, `secondary`) | No |
| `cols` values | No |
| `title`, `titleAccent`, `description`, `tag` attribute values | Yes |
| Body text inside tags | Yes |
| Table cell text (after `*`) | Yes |
| `---` row separators in tables | No |
| Standard Markdown text (paragraphs, headings, lists) | Yes |
| Code blocks (fenced with ` ``` `) | No — preserve verbatim |
| Inline code (backtick `code`) | No — preserve verbatim |
| Link paths `[text](/path)` — the path part | No |
| Link paths `[text](/path)` — the text part | Yes |
