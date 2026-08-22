---
title: Code Blocks
description: Style the wrapper, header, and copy button around a fenced code block.
---

Code Block wraps every fenced code block in your Markdown content. See [Markdown Basics](/writing-content/markdown-basics). This page covers the wrapper: its header bar, border, and copy button.

## Open the override file

```text
config/styles/code-block.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--cb-bg`
* Background of the header bar showing the language name. Defaults to `--color-surface`.
---
* `--cb-border`
* Border around the whole block and under the header bar. Defaults to `--color-border`.
---
* `--cb-radius`
* Corner radius of the whole block.
---
* `--cb-copy-button-radius`
* Corner radius of the copy button.
{% /table %}

## Example code-block.css

A `config/styles/code-block.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --cb-bg: #fafafa;
  --cb-border: #e5e5e5;
  --cb-radius: 6px;
  --cb-copy-button-radius: 4px;
}

.dark {
  --cb-bg: #161616;
  --cb-border: #2e2e2e;
}
```

You don't need to set every token like this example does. Add only the ones you actually want to change; every token left out keeps Mordoc's default.

## Next step

- [Style diagrams](/customization/advanced/diagrams).
