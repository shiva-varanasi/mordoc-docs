---
title: Assets and Branding
description: Replace the site logo, dark logo, favicon, and sharing image.
---

Mordoc uses two places for image files:

```text
config/assets/
public/
```

They have different jobs. Use `config/assets/` for the site chrome, such as logos. Use `public/` for images and files used by your content pages.

## Understand config assets

Site branding files live in:

```text
config/assets/
```

The starter project includes:

```text
config/assets/
├── logo.svg
└── logo-dark.svg
```

These files are used by the site interface, not by a specific Markdown page.

## Replace the logo

To replace the light-mode logo, replace:

```text
config/assets/logo.svg
```

Keep the filename as `logo` and use a supported image file type.

For example:

```text
config/assets/logo.svg
```

Supported image file types include SVG, PNG, JPG, and JPEG.

## Replace the dark logo

If your logo needs a different version on dark backgrounds, add or replace:

```text
config/assets/logo-dark.svg
```

The dark logo should match the light logo in size and shape as closely as possible. That helps the header feel stable when the theme changes.

## Add a favicon

A favicon is the small icon browsers show in tabs and bookmarks.

Add it here:

```text
config/assets/favicon.ico
```

You can skip this while drafting your documentation. Add it before publishing if your site should use a branded browser icon.

## Use public for content files

Do not put screenshots, diagrams, downloads, or other content files in `config/assets/`.

Those files belong in `public/`. See [Images and Files](/getting-started/images-and-files) for the full walkthrough.

## Set a sharing image

The starter project includes a sharing image:

```text
public/images/ring-og.svg
```

You can point to a sharing image from `config/site.json`:

```json
{
  "metadata": {
    "ogImage": "/images/ring-og.svg"
  }
}
```

Because the file is inside `public/`, the path starts with `/` and does not include `public`.

## Next step

[Customize theme CSS](/configuration/theme-css).
