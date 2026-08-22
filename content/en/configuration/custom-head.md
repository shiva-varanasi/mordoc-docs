---
title: Custom Head Scripts
description: Add third-party scripts, such as analytics or cookie-consent banners, to every page's HTML head.
---

Mordoc renders your `content/` markdown into HTML for you. That means there is no page where you can hand-write a `<script>` tag directly into `<head>`.

Some scripts still need to go there. Analytics, a cookie-consent or privacy banner from a third-party vendor, or a snippet your company built in-house are common examples. `config/custom-head.html` is where those go.

## Add the file

Create it here:

```text
config/custom-head.html
```

The file is optional. If it does not exist, Mordoc skips it and nothing changes.

Put whatever HTML the script needs inside it. For example, a third-party analytics snippet:

```html
<script defer src="https://analytics.example.com/script.js" data-site-id="your-site-id"></script>
```

## How Mordoc uses it

Mordoc inserts the file's contents into the `<head>` of every page, in both `mordoc dev` and `mordoc build`. Mordoc's own tags, such as `<title>` and its meta and Open Graph tags, are already in place before your content is added.

{% callout type="warning" title="Content is inserted as-is" %}
Mordoc does not check or modify what is inside `config/custom-head.html`. It is inserted exactly as written, on every page, for every visitor. Only add scripts from sources you trust.
{% /callout %}

## Next step

- [Customize your site's look](/customization/basic).
