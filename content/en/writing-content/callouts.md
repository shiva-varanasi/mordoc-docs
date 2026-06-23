---
title: Callouts
description: Highlight notes, tips, warnings, and important messages in Mordoc pages.
---

Callouts help important information stand out from the rest of the page.

Use them when a reader should pause, notice something, or be careful before continuing. Do not use a callout for every important sentence; too many callouts make a page harder to scan.

## Add a basic callout

A callout starts with `{% callout %}` and ends with `{% /callout %}`.

```markdown
{% callout type="note" title="Good to know" %}
You can keep the local preview open while you edit pages.
{% /callout %}
```

The text between the opening and closing tags is the callout content.

## Choose a type

Mordoc supports four callout types:

* `note` for useful extra context
* `tip` for helpful suggestions
* `warning` for something readers should be careful about
* `danger` for serious or risky situations

The `type` value is optional. If you leave it out, Mordoc uses `note`.

The `title` value is also optional. Add one when it helps readers understand the callout quickly.

## Note

Use `note` for helpful information that supports the main text.

```markdown
{% callout type="note" title="Good to know" %}
Mordoc updates the local preview when you save content changes.
{% /callout %}
```

## Tip

Use `tip` for advice that makes a task easier.

```markdown
{% callout type="tip" title="Writing tip" %}
Keep page titles short so they are easier to scan in navigation.
{% /callout %}
```

## Warning

Use `warning` when readers should slow down or check something before continuing.

```markdown
{% callout type="warning" title="Check the path" %}
Use page addresses like `/guides/install`, not Markdown file paths like `./install.md`.
{% /callout %}
```

## Danger

Use `danger` only for serious situations.

```markdown
{% callout type="danger" title="Do not edit generated files" %}
Do not edit files inside `dist/`. Mordoc recreates that folder when you build the site.
{% /callout %}
```

## Titles are optional

You can write a callout without a title:

```markdown
{% callout type="note" %}
This callout does not have a title.
{% /callout %}
```

Use a title when it helps the reader understand the message quickly.

## Keep callouts short

A good callout is usually one short paragraph or a small list. If the callout becomes long, it may need to be a normal section instead.

## Next step

* [Create tables](/writing-content/tables).
