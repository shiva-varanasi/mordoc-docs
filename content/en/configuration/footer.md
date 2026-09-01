---
title: Footer
description: Configure the columns of links and text shown at the bottom of every page.
---

Every Mordoc site has a footer. Without any configuration, it shows a single "Powered by Mordoc" line. You can replace that with your own columns of links and text.

## Create the footer file

The footer lives in this optional file:

```text
config/navigation/footer.yaml
```

Create the file only when you want to replace the default footer.

## Add footer columns

The footer has three named columns — `start`, `center`, and `end`, rendered left to right in that order. All three are optional:

```yaml
start:
  - "[Privacy policy](/privacy)"
  - Powered by [Mordoc](https://mordoc.dev)
center:
  - "[Support](/support)"
end:
  - "© 2026 Acme Inc."
```

Each column is a list of lines, stacked top to bottom. A line is plain text, plain text with a link, or a mix.

## Add a link inside a line

Use Markdown-style link syntax anywhere in a line:

```yaml
- "[Privacy policy](/privacy)"
```

Everything outside the brackets renders as plain text; the bracketed part becomes a link. External links (starting with `http://`, `https://`, or `//`) open in a new tab; anything else is treated as a route on your own site.

{% callout type="warning" title="Quote lines that start with a link" %}
A line starting with an unquoted `[` is read by YAML as the start of a list, not text:

```yaml
# Wrong — YAML sees a list, not a footer line
- [Privacy policy](/privacy)

# Right — quoted, so YAML reads it as one string
- "[Privacy policy](/privacy)"
```
{% /callout %}

## Turn the footer off

Add the file with no zones, or all-empty zones, and Mordoc renders no footer at all. This is different from leaving the file out entirely, which falls back to the default "Powered by Mordoc" line:

## Translate footer lines

Footer lines are translated the same way navigation labels are, in `config/navigation/translations/<lang>.yaml`. See [Navigation Translations](/configuration/navigation-translations) for the full syntax, including how internal links inside a footer line need their path prefixed by hand for each language.

## Save and check the footer

Save `config/navigation/footer.yaml`.

If your local server is running, scroll to the bottom of any page to see the change.

## Next step

[Configure languages](/configuration/languages).
