---
title: Building Your Site
description: Learn how to build your Mordoc documentation site for production deployment.
---

Building your Mordoc documentation site compiles your markdown content into optimized static HTML files ready for deployment.

# Build Command

Build your documentation site:

```bash
npm run build
```

This command:
1. Processes all markdown files
2. Generates HTML pages
3. Compiles and minifies CSS/JavaScript
4. Optimizes images
5. Creates search index
6. Outputs to `dist/` directory

## Build Output

```bash
$ npm run build

> mordoc build

✓ Processing markdown files...
✓ Generating pages...
✓ Building search index...
✓ Optimizing assets...
✓ Build complete!

Output: dist/
Pages: 24
Build time: 2.4s
```

# Output Directory

The build generates a `dist/` directory containing your complete static site:

```
dist/
├── index.html
├── get-started/
│   ├── index.html
│   └── creating-project/
│       └── index.html
├── assets/
│   ├── styles.css
│   ├── main.js
│   └── fonts/
├── images/
├── icons/
├── pagefind/           # Search index
│   ├── pagefind.js
│   └── ...
└── config.json
```