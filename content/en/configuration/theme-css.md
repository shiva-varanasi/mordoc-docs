---
title: Theme CSS
description: Adjust your Mordoc site's colors, fonts, and other visual settings with theme CSS.
---

Mordoc gives you a working design by default.

You do not need to write CSS to create pages, add navigation, or publish documentation. When you are ready to match your company's branding, use `config/styles/theme.css`.

## Open the theme file

Theme CSS lives here:

```text
config/styles/theme.css
```

The starter project includes this file. In the Ring of Power example, it looks like this:

```css
:root {
  --accent: #D64518;
}
```

## Change the accent color

Replace the value of `--accent` with your brand color:

```css
:root {
  --accent: #2563eb;
}
```

Save the file. If your local server is running, refresh the browser to see the change.

## Set a different accent for dark mode

If your brand color does not have enough contrast on a dark background, override `--accent` again inside a `.dark` selector:

```css
:root {
  --accent: #2563eb;
}

.dark {
  --accent: #60a5fa;
}
```

Mordoc adds the `dark` class to the page when the reader switches to dark mode, so this second value only applies there. The `:root` value covers light mode as before.

## How the accent color spreads through the site

`--accent` is the one color Mordoc asks you to set. Every other accent shade on the site, such as the lighter tint behind an active navigation item or the darker shade a button turns on hover, is calculated automatically from that single value.

This means changing `--accent` updates links, buttons, active navigation states, card tags, and similar details across the whole site at once. Each mode recalculates its shades from whichever `--accent` is active for that mode, so light and dark mode stay consistent even if you've set them to different colors. You do not need to hunt down and set each one by hand.

## Keep the file small

Add only the rules you understand.

A short theme file is easier to maintain when you update Mordoc or change branding later.

## Do not edit generated files

Theme changes belong in:

```text
config/styles/theme.css
```

Do not edit CSS files inside `dist/`. The `dist/` folder is generated when you build the site, and Mordoc can replace it on the next build.

## Next step

- [Custom head scripts](/configuration/custom-head).
