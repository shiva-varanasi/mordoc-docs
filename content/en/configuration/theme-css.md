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

Mordoc loads this file automatically. You do not need to import it anywhere else.

## Change the accent color

The most common theme change is the accent color.

Replace the value of `--accent` with your brand color:

```css
:root {
  --accent: #2563eb;
}
```

Mordoc uses `--accent` across the site for links, active navigation states, buttons, and other emphasis.

You do not need to set every related color by hand. Mordoc derives lighter and darker accent shades from `--accent` for you.

Save the file. If your local server is running, refresh the browser to see the change.

## How theme CSS works

Mordoc uses CSS variables for its design.

Your theme file overrides those variables in `:root`:

```css
:root {
  --accent: #2563eb;
  --font-sans: 'Inter', system-ui, sans-serif;
}
```

For dark mode, use the `.dark` selector:

```css
.dark {
  --color-bg: #121212;
  --color-fg: #e2e8f0;
}
```

Mordoc adds the `dark` class to the page when the reader switches to dark mode.

## Common global settings

These variables are a good starting point for light branding changes:

* `--accent` for links, buttons, active navigation, and other emphasis
* `--color-bg` for the main page background
* `--color-surface` for subtle background areas, such as blockquotes
* `--color-border` for borders and dividers
* `--color-fg` for main text color
* `--color-content-fg` for body text in documentation pages
* `--color-fg-muted` for secondary text, such as descriptions
* `--font-sans` for the main site font
* `--font-mono` for inline code and code blocks
* `--content-max-width` for the maximum width of page content
* `--page-gutter` for horizontal spacing on landing pages

Start with `--accent`. Add more variables only when you need finer control.

## Advanced component settings

Mordoc also defines variables for specific parts of the site, such as the sidebar, header, and callouts.

For example:

* `--sidenav-bg` and `--sidenav-fg` for the sidebar
* `--callout-note-accent` and similar variables for callout colors

You can override these in `config/styles/theme.css` when you need deeper customization.

For most company documentation sites, the global settings above are enough.

## Prefer content settings first

Before changing CSS, check whether the page or component already has the option you need.

For example:

* Landing pages can set hero colors and backgrounds.
* Cards can use icons and images.
* Callouts already have built-in types.

Use theme CSS when you want site-wide visual changes, not when you are trying to style one page differently.

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

* [Change management with Git](/publishing/change-management).
