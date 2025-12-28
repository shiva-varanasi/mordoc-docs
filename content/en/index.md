---
title: Overview
description: Create powerful documentation websites with Mordoc - an open-source tool that lets you write in markdown and deploy anywhere.
---

Mordoc is an **open-source documentation generator** that transforms markdown into beautiful, functional documentation websites using Markdoc.

Write your content in markdown. Deploy to any infrastructure. No vendor lock-in.

> **Freedom to Deploy:** Mordoc generates static sites that work anywhere — your servers, cloud platforms, or edge networks. You own your deployment.

# Why Mordoc?

{% cardGrid cols="3" %}
{% card title="Write in Markdown" href="/syntax-components/headings" %}
Use familiar markdown syntax with powerful Markdoc extensions for rich content like callouts, cards, and interactive components.
{% /card %}

{% card title="Deploy Anywhere" href="/deployment/launch" %}
Generate static HTML that works on any hosting platform. No proprietary infrastructure required.
{% /card %}

{% card title="Customizable Styling" href="/configuration/branding" %}
Modern, responsive design with customizable colors, typography, and component styles through JSON configuration.
{% /card %}
{% /cardGrid %}

# Key Features

- **Markdoc-Based**: Built on Markdoc for powerful markdown extensions
- **Infrastructure Independent**: Deploy to any static hosting platform
- **Customizable Components**: Style cards, navigation, links, and more with JSON config
- **Auto-Generated Features**: Built-in search with Pagefind, table of contents, and navigation
- **Developer-Friendly**: Simple CLI tools and familiar workflows
- **Dark Mode Support**: Automatic dark mode with customizable colors

---

# Quick Start

Get started with Mordoc in minutes:

```bash
npx create-mordoc-app my-docs
cd my-docs
npm run dev
```

Your documentation site will be running at `http://localhost:3000`.

# What You'll Build

With Mordoc, you can create documentation that includes:

| Feature | Description |
|---|---|
| Rich Navigation | Multi-level side navigation with parent-child relationships |
| Search | Auto-generated Pagefind search functionality |
| Code Blocks | Syntax-highlighted code examples via Markdoc |
| Callouts | Styled note, warning, and danger boxes |
| Cards & Grids | Visual card components for feature showcases |
| Custom Branding | Logo, favicon, and customizable colors |

# Next Steps

{% callout type="note" title="New to Mordoc?" %}
Follow the **Get Started** guide to create your first documentation project and understand the project structure.
{% /callout %}

Ready to build your documentation? Start with the prerequisites:

1. [Install a code editor](/prerequisites/code-editor)
2. [Install Node.js](/prerequisites/nodejs)
3. [Install Git](/prerequisites/git)
4. [Create your first project](/get-started/creating-project)

