---
title: Build Your Site
description: Turn your Mordoc project into a finished static website ready to publish.
---

When you are ready to publish, Mordoc needs to create a production version of your documentation site.

This step is called a build.

## Run the build

From your project folder, run:

```bash
npm run build
```

Mordoc reads your content and configuration, then creates a finished website inside `dist/`.

Building does not publish your site. It only prepares the files you will upload later.

## What the build creates

During the build, Mordoc:

* Reads Markdown pages from `content/`
* Applies your site settings from `config/`
* Renders each page as static HTML
* Copies images and files from `public/`
* Copies branding files from `config/assets/`
* Creates a search index for the site header search
* Writes `sitemap.xml` and `robots.txt`

The result is a static website. Each page is a file that a web server can serve directly.

## The dist folder

After a successful build, Mordoc creates:

```text
dist/
```

This folder contains your finished documentation website.

For example:

```text
dist/
├── index.html
├── lore/
│   └── index.html
├── sitemap.xml
├── robots.txt
├── pagefind/
└── assets/
```

Do not edit files in `dist/` by hand. If you need to change the site, edit the source files in `content/`, `config/`, or `public/`, then build again.

## Set baseUrl before you build

Before publishing, make sure `config/site.json` has the correct public URL in `baseUrl`:

```json
{
  "baseUrl": "https://docs.example.com"
}
```

Mordoc uses this value when it generates `sitemap.xml`, `robots.txt`, and page metadata during the build.

Use your real production address, not a local preview address such as `http://localhost:5173`.

See [Site Configuration](/configuration/site-configuration) if you need to update this setting.

## Next step

[Preview the built site](/publishing/preview-before-publishing).
