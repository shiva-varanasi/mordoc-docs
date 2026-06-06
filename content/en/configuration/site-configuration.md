---
title: Site Configuration
description: Set the basic name, description, language, and public URL for your Mordoc site.
---

Your Mordoc site has one main settings file:

```text
config/site.json
```

This file tells Mordoc basic information about your documentation site. You do not need to change every setting at once. Start with the fields that readers and search engines will see first.

## Open site.json

In the starter project, `config/site.json` looks like this:

```json
{
  "name": "The Ring of Power",
  "description": "A field guide for keepers, scholars, and reluctant bearers of the One Ring.",
  "baseUrl": "https://ring-of-power.example.com",
  "defaultLanguage": "en"
}
```

The values are part of the starter example. You will replace them with details for your own documentation.

## Change the site name

The `name` field is the name of your documentation site.

```json
{
  "name": "Acme Docs"
}
```

Choose a short name that readers will recognize. This is usually your product name, project name, or team documentation name.

## Change the description

The `description` field is a short summary of the site.

```json
{
  "description": "Guides and reference material for Acme users."
}
```

Keep it calm and direct. One sentence is enough.

This description can appear in page metadata and link previews, depending on the page and site settings.

## Set the public URL

The `baseUrl` field is the public address where the site will live.

```json
{
  "baseUrl": "https://docs.example.com"
}
```

Use the final website address if you know it.

If you are still learning locally, you can leave the starter value for now and come back before publishing.

Do not use your local preview address, such as `http://localhost:5173`, as the final `baseUrl`.

## Keep the default language

The `defaultLanguage` field tells Mordoc which language folder is the main one.

```json
{
  "defaultLanguage": "en"
}
```

In the starter project, your pages are inside:

```text
content/en/
```

That is why the default language is `en`.

You do not need to change this unless you are making a site whose main language is not English.

## Save the file

After changing `config/site.json`, save the file.

If your local server is running, refresh the browser if you do not see the change right away.

## Metadata for SEO and sharing

`config/site.json` can also include site-wide metadata:

```json
{
  "metadata": {
    "ogImage": "/images/ring-og.svg",
    "ogType": "website",
    "twitterCard": "summary_large_image",
    "twitterSite": "@example"
  }
}
```

These settings help search engines and social sites understand your documentation website.

They are especially important for company documentation, where readers may find pages through search results, shared links, chat previews, or social posts.

Start with `ogImage`. It points to an image in `public/` that can appear when someone shares your site link.

For example, this value:

```json
{
  "metadata": {
    "ogImage": "/images/ring-og.svg"
  }
}
```

Points to this file:

```text
public/images/ring-og.svg
```

The other metadata fields control the kind of preview that external services may show.

A later page on [SEO and search](/publishing/seo-and-search) will explain how these settings work with page descriptions, generated search indexes, `sitemap.xml`, and `robots.txt`.

## Next step

[Configure the side navigation](/configuration/side-navigation).
