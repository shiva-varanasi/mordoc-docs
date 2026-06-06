---
title: SEO and Search
description: Understand how Mordoc helps search engines, social sharing, and on-site search work.
---

Mordoc helps your documentation site work well in search results, link previews, and the built-in site search.

Most of this happens automatically when you build the site. A few settings in your project help search engines and social sites understand your content.

## Write useful page descriptions

Each page can include an optional `description` in its frontmatter:

```markdown
---
title: Install the App
description: Install the app and confirm it runs on your machine.
---
```

When you build the site, Mordoc uses this value in two ways:

* It adds a `<meta name="description">` tag for that page.
* It uses the page description in Open Graph and Twitter preview tags.

If a page does not have a `description`, Mordoc does not add `<meta name="description">` for that page.

For social preview tags, Mordoc falls back to the site-wide `description` from `config/site.json`.

On normal documentation pages, the description also appears under the page title for readers. Landing pages do not show the frontmatter description on the page itself, but it can still be used in built page metadata when you provide it.

## Set site-wide metadata

Site-wide sharing settings live in `config/site.json`.

The most important fields for publishing are:

* `name` and `description` for the overall site
* `baseUrl` for the public website address
* `metadata.ogImage` for the image shown when someone shares your site link

For example:

```json
{
  "name": "Acme Docs",
  "description": "Guides and reference material for Acme users.",
  "baseUrl": "https://docs.example.com",
  "metadata": {
    "ogImage": "/images/ring-og.svg",
    "ogType": "website",
    "twitterCard": "summary_large_image",
    "twitterSite": "@example"
  }
}
```

The `ogImage` path points to a file in `public/`, such as:

```text
public/images/ring-og.svg
```

See [Site Configuration](/configuration/site-configuration) for a full walkthrough of these fields.

## What Mordoc generates at build time

When you run `npm run build`, Mordoc adds SEO and search files to `dist/`.

### Page metadata

Each built page includes metadata such as:

* A page title in the format `Page Title — Site Name`
* A page description meta tag, when the page frontmatter includes `description`
* Canonical links based on `baseUrl`
* Open Graph tags, including `og:description`
* Twitter Card tags when `metadata.twitterCard` is set in `config/site.json`

If a page has no frontmatter description, social preview tags can still use the site-wide description from `config/site.json`.

### sitemap.xml

Mordoc writes `dist/sitemap.xml` with a URL entry for every page in your project.

Search engines use this file to discover your documentation pages.

The URLs come from your content files and `baseUrl`.

### robots.txt

Mordoc also writes `dist/robots.txt`.

This file tells search engines they may crawl your site and points them to `sitemap.xml`.

### Search index

Mordoc uses [Pagefind](https://pagefind.app/) for on-site search.

Pagefind is a static search tool. It reads your built HTML pages and creates a search index that runs entirely in the browser. That means readers can search your documentation without a separate search server.

When you run `npm run build`, Mordoc builds this index automatically after the static HTML files are created.

For a single-language site, the index is written to:

```text
dist/pagefind/
```

For multilingual sites, Mordoc creates one index per language, such as:

```text
dist/pagefind-en/
dist/pagefind-fr/
```

This powers the search box in the site header. When a reader switches languages, Mordoc loads the matching index for that language.

Pagefind indexes the main page content and page titles from your built HTML. It does not use frontmatter descriptions as a separate search field.

Search only works after you build the site. The dev server does not have search support.

## Next step

[Deploy your site](/publishing/deploy-your-site).
