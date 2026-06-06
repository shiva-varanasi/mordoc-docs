---
title: Top Navigation
description: Split a larger Mordoc site into major documentation areas, each with its own sidebar.
---

Top navigation is for larger documentation sites that need more than one main area.

For example, a company might have one documentation site with separate areas for different products, teams, or manuals. Each area can have its own side navigation tree.

If your documentation has one simple sidebar, you do not need top navigation. Use [Side Navigation](/configuration/side-navigation) instead.

## Create the top navigation file

Top navigation is optional. If you want to use it, create this file:

```text
config/navigation/topnav.yaml
```

Each top navigation item points to a documentation area and names the side navigation file for that area:

```yaml
- label: Field Manual
  path: /field-manual
  sidenav: field-manual.yaml

- label: Ship Systems
  path: /ship-systems
  sidenav: ship-systems.yaml
```

Each item needs:

* `label` for the text readers see in the top navigation
* `path` for the page that opens when readers click the top navigation item
* `sidenav` for the side navigation file that belongs to that area

The `path` should usually be the starting page for that documentation area. It can be an overview page in the matching side navigation tree, or a landing page that introduces that area.

## Add the side navigation files

The files named by `sidenav` live in the same navigation folder:

```text
config/navigation/
├── topnav.yaml
├── field-manual.yaml
└── ship-systems.yaml
```

When you use `topnav.yaml`, these named files replace the single site-wide `sidenav.yaml` pattern.

Each named side navigation file uses the same structure as `sidenav.yaml`.

For example, `config/navigation/field-manual.yaml` might contain:

```yaml
- label: Field Manual
  expanded: true
  children:
    - label: Overview
      path: /field-manual
    - label: Safety Rules
      path: /field-manual/safety-rules
    - label: Emergency Procedures
      path: /field-manual/emergency-procedures
```

And `config/navigation/ship-systems.yaml` might contain:

```yaml
- label: Ship Systems
  expanded: true
  children:
    - label: Overview
      path: /ship-systems
    - label: Engines
      path: /ship-systems/engines
    - label: Navigation Console
      path: /ship-systems/navigation-console
```

## How Mordoc chooses the sidebar

When `topnav.yaml` exists, Mordoc uses the top navigation items to choose which sidebar to show.

If the reader is on a page under this route:

```text
/field-manual
```

Mordoc uses:

```text
config/navigation/field-manual.yaml
```

If the reader is on a page under this route:

```text
/ship-systems
```

Mordoc uses:

```text
config/navigation/ship-systems.yaml
```

That means each major documentation area can have a focused sidebar.

## Use route paths

The `path` in `topnav.yaml` should be a route in your site:

```yaml
- label: Field Manual
  path: /field-manual
  sidenav: field-manual.yaml
```

Do not use a Markdown file path:

```yaml
- label: Field Manual
  path: /content/en/field-manual/index.md
  sidenav: field-manual.yaml
```

## Keep the list short

Top navigation works best when it contains a few major documentation areas.

Good top navigation labels might be:

* `Field Manual`
* `Ship Systems`
* `Crew Handbook`

Do not put every page in top navigation. Put pages inside the side navigation file for the area they belong to.

For the available side navigation fields, see [Side Navigation](/configuration/side-navigation).

## Save and check the header

Save `config/navigation/topnav.yaml`.

If your local server is running, check the top area of the site. You should see your top navigation labels.

Click each top navigation item and make sure the sidebar changes to the matching area.

## Next step

[Configure header links](/configuration/header-links).
