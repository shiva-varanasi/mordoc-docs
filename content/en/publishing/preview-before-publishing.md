---
title: Preview Before Publishing
description: Check your built documentation site locally before you deploy it.
---

After you build your site, take a moment to preview the files in `dist/` before publishing them.

This is different from `npm run dev`.

## Dev and build preview are different

While you are writing documentation, use:

```bash
npm run dev
```

That command is for day-to-day editing. It shows your latest content and configuration while you work.

After you run `npm run build`, you should preview the built files in `dist/` instead. That preview shows the same static site you will publish.

## Preview the dist folder

Build the site first:

```bash
npm run build
```

Then serve the `dist/` folder with a static file server.

For a quick local check, you can run:

```bash
npx serve dist
```

Open the URL shown in your terminal, usually something like:

```text
http://localhost:3000
```

Browse the site the way a reader would.

## What to check

Before you deploy, verify:

* Pages open correctly from the sidebar and links
* Images and downloads load as expected
* The homepage and landing pages look right
* Search works in the site header
* The site name, logo, and theme look correct

If something is wrong, fix the source files in your project, run `npm run build` again, and preview once more.

## Next step

- [Review SEO and search settings](/publishing/seo-and-search).
