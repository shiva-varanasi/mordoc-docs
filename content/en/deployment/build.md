---
title: Build Your Site
description: Learn what building means in Mordoc and how your documentation is prepared for publishing.
---

Before your documentation can be published, Mordoc needs to convert your content into a production‑ready format. This process is called **building**.

# Build command

To build your documentation site, run:

```bash
npm run build
```

This command prepares your documentation for previewing and deployment.

# What does Build mean?

When you build your site, Mordoc takes everything you have written and configured and transforms it into a finished website made of static files.

During the build process, Mordoc:

* Reads markdown files from the `content/` directory
* Applies your navigation structure from `config/sidenav.yaml`
* Converts markdown into static HTML pages
* Bundles and optimizes styles and browser-side JavaScript
* Processes images and other assets
* Generates files required for search
* Produces a complete version of your site ready to be served

The result is a static website where pages are served directly as files, without any server‑side code running.

# Build output

After the build completes, Mordoc generates a directory named `dist/`.

This directory contains:

* HTML files for every documentation page
* Optimized CSS and JavaScript files
* Images, fonts, and icons
* Search index files

The `dist/` directory represents your finished documentation website.

{% callout type="note" %}
The build process does not publish your site. It only prepares the files needed for previewing and deployment.
{% /callout %}

# Next steps

* [Preview & Test](/deployment/preview)
* [Version Control with Git](/deployment/version-control)
* [Deploy](/deployment/deploy)