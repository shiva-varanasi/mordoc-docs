---
title: Advanced
description: Target design tokens for individual parts of Mordoc's UI, from the overall page layout down to a single component.
---

Basic customization changes one color and, optionally, one font. Advanced customization goes further: every visual part of a Mordoc site, down to a single button or callout, has its own set of design tokens you can override without touching a component's actual structure or behavior.

## How overrides are layered

A Mordoc site's CSS is built from three layers, in this order:

1. **Mordoc's defaults**: the built-in look, so a new site already works with zero configuration.
2. **`config/styles/theme.css`**: your site-wide overrides from [Basic customization](/customization/basic): `--accent`, and the handful of global tokens covered in [Design Tokens](/customization/advanced/design-tokens).
3. **`config/styles/<component>.css`**: one optional file per component, each overriding only that component's own tokens.

Each layer only needs to contain the values you want to change. A later layer wins over an earlier one, so a color set in `theme.css` becomes that component's default everywhere, and a color set in the component's own file wins for that component alone. If a file doesn't exist, Mordoc simply skips it. Nothing breaks.

## One page per file, one file per part of the UI

Every page in this section documents exactly one file under `config/styles/`, and every file targets exactly one part of the interface, the same one-to-one mapping Mordoc uses internally. If you have `config/styles/header.css` open, [Header](/customization/advanced/header) is the page that documents every token you can put in it.

## Read it the way Mordoc is built

The pages are ordered to match how Mordoc's own UI is put together, zooming in one level at a time:

1. **[Design Tokens](/customization/advanced/design-tokens)**: the remaining global colors, beyond `--accent`, that everything else defaults to.
2. **[App Layout](/customization/advanced/app-layout)**: the three boxes every page is built from: the header, the side navigation, and the content area.
3. **Header, and everything inside it**: the header's own skeleton, then each piece it's made of: header links, top navigation, the language picker, the theme toggle, and search.
4. **Side Navigation**: the sidebar box next to it.
5. **Content, and everything inside it**: the content area's own skeleton, then the article page, table of contents, and every component you can place in a Markdown page: callouts, accordions, cards, code blocks, diagrams, images, and the landing-page pieces (hero, sections, buttons).

You don't need to read every page. Jump straight to the one part of the UI you want to change. Its page lists only the tokens that apply to it.

## Next step

- [Set global design tokens](/customization/advanced/design-tokens).
