---
title: Header Links
description: Add compact links to external destinations such as repositories, API reference, or login pages.
---

Header links are optional links shown in the site header.

They are useful for destinations outside the documentation site that readers may need often.

For example, you might link to a source repository, hosted API reference, support portal, or your company's sign in page.

## Create the header navigation file

Header links live in this optional file:

```text
config/navigation/headernav.yaml
```

Create the file only when you need header links.

## Add a link

Start with a small list:

```yaml
- label: GitHub
  path: https://github.com/example/project

- label: API Reference
  path: https://api.example.com

- label: Sign in
  path: https://app.example.com/login
  variant: primary
```

Use `label` for the visible text.

Use `path` for the full website address.

Use `variant` when a link should look like a button. The value can be `link`, `primary`, or `secondary`.

## Choose links carefully

Header links should feel useful, not crowded.

Common choices include:

* A source repository
* An API reference hosted outside Mordoc
* A support portal
* A community page
* A sign in or sign up page

For normal documentation pages, use the [side navigation](/configuration/side-navigation).

For separate documentation areas with their own sidebars, use [top navigation](/configuration/top-navigation).

## Use full URLs

Header links usually point outside the documentation site, so use the full URL:

```yaml
- label: Support
  path: https://example.com/support
```

## Save and check the header

Save `config/navigation/headernav.yaml`.

If your local server is running, check the header area of the site and make sure each link goes where you expect.

## Next step

[Configure the footer](/configuration/footer).
