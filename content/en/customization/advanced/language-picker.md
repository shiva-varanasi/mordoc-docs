---
title: Language Picker
description: Style the language switcher shown in the header on multi-language sites.
---

The language picker only renders when a site has more than one language configured. See [Languages](/configuration/languages). `config/styles/language-picker.css` styles its trigger button and dropdown.

## Open the override file

```text
config/styles/language-picker.css
```

## Tokens

{% table %}
* Token
* What it controls
---
* `--lang-height`
* Height of the trigger button.
---
* `--lang-padding`
* Horizontal padding of the trigger button.
---
* `--lang-gap`
* Gap between the globe icon and language code in the trigger.
---
* `--lang-radius`
* Corner radius of the trigger button.
---
* `--lang-font-size`
* Font size of the trigger and dropdown options.
---
* `--lang-icon-size`
* Size of the globe icon.
---
* `--lang-fg`
* Trigger text color.
---
* `--lang-fg-hover`
* Trigger text color on hover.
---
* `--lang-bg-hover`
* Trigger background on hover.
---
* `--lang-active-color`
* Text color of the currently selected language in the dropdown.
---
* `--lang-active-bg`
* Background of the currently selected language in the dropdown.
---
* `--lang-dropdown-radius`
* Corner radius of the dropdown panel.
---
* `--lang-dropdown-shadow`
* Drop shadow under the dropdown panel.
---
* `--lang-option-radius`
* Corner radius of each option row in the dropdown.
{% /table %}

## Example language-picker.css

A `config/styles/language-picker.css` that sets every token on this page, for both light and dark mode:

```css
:root {
  --lang-height: 36px;
  --lang-padding: 10px;
  --lang-gap: 6px;
  --lang-radius: 999px;
  --lang-font-size: 14px;
  --lang-icon-size: 16px;
  --lang-fg: #383838;
  --lang-fg-hover: #1c1c1c;
  --lang-bg-hover: #f5f5f5;
  --lang-active-color: #0f766e;
  --lang-active-bg: #f0fdfa;
  --lang-dropdown-radius: 8px;
  --lang-dropdown-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.07), 0 2px 4px -1px rgba(0, 0, 0, 0.04);
  --lang-option-radius: 4px;
}

.dark {
  --lang-fg: #9e9e9e;
  --lang-fg-hover: #ebebeb;
  --lang-bg-hover: #1f1f1f;
  --lang-active-color: #2dd4bf;
  --lang-active-bg: #0f2e2b;
}
```

You don't need to set every token like this example does. Add only the ones you actually want to change; every token left out keeps Mordoc's default.

## Next step

- [Style the theme toggle](/customization/advanced/theme-toggle).
