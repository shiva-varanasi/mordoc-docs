---
title: Font Family
description: Replace Mordoc's default typeface for body text and code with your own font files.
---

Mordoc renders body text in `Inter` and code in a default monospace stack.

If your brand has its own typeface, you can register it in `config/site.json` and Mordoc will use it everywhere that role appears: body text, headings, navigation, and buttons for one role, code blocks and inline code for the other.

## Step 1 - Add the font files

Font files live here:

```text
config/assets/fonts/
```

Add one file per style you have: a regular weight and, optionally, an italic. Mordoc expects **variable fonts** (a single file that covers a whole weight range, `100`–`900`), not one file per weight.

Supported file types are `.woff2`, `.woff`, and `.ttf`. `.woff2` is smaller and loads faster, so prefer it when your font provider offers a choice.

For example:

```text
config/assets/fonts/
├── SpaceGrotesk.woff2
├── SpaceMono.woff2
└── SpaceMono-Italic.woff2
```

## Step 2 - Register the font in site.json

Add a `fonts` field to `config/site.json` with one slot per role:

```json
{
  "fonts": {
    "body": {
      "family": "Space Grotesk",
      "regular": "SpaceGrotesk.woff2"
    },
    "code": {
      "family": "Space Mono",
      "regular": "SpaceMono.woff2",
      "italic": "SpaceMono-Italic.woff2"
    }
  }
}
```

* `family`: the font's name, used to register it and assign it to the role.
* `regular`: filename of the normal-weight file, resolved against `config/assets/fonts/`.
* `italic`: filename of the italic file. Optional; omit it if you don't have one.

Save and refresh. Body text and code now both render in their new fonts.

## The two font roles

`fonts` has two independent slots:

{% table %}
* Slot
* Used for
---
* `body`
* Body text, headings, navigation, and buttons across the site.
---
* `code`
* Code blocks and inline code.
{% /table %}

You can declare one slot without the other. A project that only wants a custom heading/body face, and is happy with the default monospace stack for code, would only add `fonts.body`:

```json
{
  "fonts": {
    "body": {
      "family": "Space Grotesk",
      "regular": "SpaceGrotesk.woff2"
    }
  }
}
```

Any slot you leave out falls back to Mordoc's default for that role: Inter for `body`, the default system-monospace stack for `code`. Nothing breaks if you never add a `fonts` field at all.

{% callout type="note" title="Regular-only is fine" %}
`italic` is optional on both slots. If you only supply `regular`, Mordoc synthesizes italics from it the same way a browser would for any font that has no dedicated italic file.
{% /callout %}

## Next step

- [Advanced customization](/customization/advanced).
