---
title: Navigation Translations
description: Translate navigation labels for multilingual Mordoc sites.
---

Navigation translations are only needed when your site has more than one language.

If your site only uses `content/en/`, you can skip this page for now and come back later.

## What gets translated

Your navigation files define the structure of the navigation:

```text
config/navigation/sidenav.yaml
config/navigation/topnav.yaml
config/navigation/headernav.yaml
```

Translation files let you change the visible labels for another language without rebuilding the whole navigation structure from scratch.

## Create a translations folder

Navigation translation files live here:

```text
config/navigation/translations/
```

Create one YAML file for each translated language.

For example, a French translation file would be:

```text
config/navigation/translations/fr.yaml
```

## Add translated labels

Use the original labels as keys, then provide the translated labels as values:

```yaml
Getting Started: Premiers pas
Writing Content: Rediger du contenu
Configuration: Configuration
```

When Mordoc shows the French version of the site, it can use these translated labels in navigation.

## Keep labels matched

The keys in the translation file should match the labels used in your navigation files.

For example, if `sidenav.yaml` contains:

```yaml
- label: Getting Started
  children:
    - label: Create a Project
      path: /getting-started/create-project
```

Then the translation file can contain:

```yaml
Getting Started: Premiers pas
Create a Project: Creer un projet
```

If a label is missing from the translation file, Mordoc can still show the original label.

## Translate footer lines

If you've configured a [Footer](/configuration/footer), its lines are translated in this same file, using the same key-value format. Key on the exact line from `footer.yaml`, including any `[text](url)` link syntax:

```yaml
"Powered by [Mordoc](https://mordoc.dev)": "Bereitgestellt von [Mordoc](https://mordoc.dev)"
"[Privacy policy](/privacy)": "[Datenschutzrichtlinie](/privacy)"
```

Quote both sides when the line contains a link — the same reason `footer.yaml` itself needs quoting: an unquoted leading `[` reads as a YAML list.

Unlike sidenav and topnav paths, which Mordoc prefixes with the language code automatically, a footer line's path is part of the translated string itself. Prefix it by hand for an internal link:

```yaml
"[Privacy policy](/privacy)": "[Politique de confidentialité](/fr/privacy)"
```

## Start with languages first

Navigation translations make the most sense after your site has more than one language folder, such as:

```text
content/
├── en/
└── fr/
```

If you have not done that yet, start with [Languages](/configuration/languages).

## Next step

[Configure variables](/configuration/variables).
