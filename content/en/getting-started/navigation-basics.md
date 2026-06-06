---
title: Navigation Basics
description: Add pages to the Mordoc side navigation so readers can find them.
---

In the previous steps, you created a page at:

```text
/my-first-page
```

The page exists, but it does not appear in the sidebar yet. Mordoc keeps pages and navigation separate so you can choose which pages readers see in the menu.

In this step, you will add your new page to the sidebar.

## Open the navigation file

Open this file:

```text
config/navigation/sidenav.yaml
```

The starter file looks like this:

```yaml
- label: The Ring
  expanded: true
  children:
    - label: Lore of the Ring
      path: /lore
    - label: Wielding the Ring
      path: /wielding-the-ring
    - label: Safeguards
      path: /safeguards
```

This file controls the links shown in the sidebar.

## Add your page

Add your new page under `children`:

```yaml
- label: The Ring
  expanded: true
  children:
    - label: Lore of the Ring
      path: /lore
    - label: Wielding the Ring
      path: /wielding-the-ring
    - label: Safeguards
      path: /safeguards
    - label: My First Page
      path: /my-first-page
```

Save the file.

If your local server is running, the sidebar should update automatically. You should now see `My First Page` in the sidebar.

## What label and path mean

Each navigation item has a `label` and a `path`.

```yaml
- label: My First Page
  path: /my-first-page
```

The `label` is what readers see in the sidebar.

The `path` is the page address that opens when they click the label.

## Keep labels simple

Navigation labels should be short and clear.

Good examples:

* `Install`
* `Configuration`
* `Deploy`

Avoid long labels when a shorter one is clear enough.

## More navigation options

This page only covers the first sidebar edit.

Later, the [Side Navigation](/configuration/side-navigation) page will explain nested groups and expanded groups. The Configuration section will also explain top navigation, header links, and translated navigation labels.

## Next step

[Add images and files](/getting-started/images-and-files).
