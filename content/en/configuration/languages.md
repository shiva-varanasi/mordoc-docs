---
title: Languages
description: Understand how Mordoc uses language folders and optional language settings.
---

Mordoc uses folders inside `content/` to organize languages.

The starter project has one language:

```text
content/
└── en/
```

That means the starter site is written in English.

## Understand the default language

The default language is set in `config/site.json`:

```json
{
  "defaultLanguage": "en"
}
```

Because `en` is the default language, pages inside `content/en/` do not get a language prefix in their routes.

For example:

```text
content/en/index.md          -> /
content/en/guides/index.md   -> /guides
content/en/guides/install.md -> /guides/install
```

## Add another language folder

If you add another language, create another folder inside `content/`.

For example:

```text
content/
├── en/
└── fr/
```

Pages in non-default languages use the language code as a route prefix.

```text
content/fr/index.md          -> /fr
content/fr/guides/index.md   -> /fr/guides
content/fr/guides/install.md -> /fr/guides/install
```

## Keep page structure the same

Keep the same folder and file structure in each language:

```text
content/
├── en/
│   └── guides/
│       └── install.md
└── fr/
    └── guides/
        └── install.md
```

This is required because the site uses one navigation structure for all languages.

The side navigation and top navigation point to routes such as:

```text
/guides/install
```

When a reader switches languages, Mordoc uses the matching route in the selected language.

For example:

```text
content/en/guides/install.md -> /guides/install
content/fr/guides/install.md -> /fr/guides/install
```

## Missing language content

If a language is listed in `config/language.json` but its content folder is missing or empty, Mordoc can fall back to the default language content at runtime.

For example, if `fr` is listed here:

```json
{
  "languages": ["en", "fr"]
}
```

But this folder does not exist yet:

```text
content/fr/
```

Mordoc can still use the default language content.

This fallback is helpful while translations are in progress, but translated content should still follow the same folder and file structure when you add it.

## Add the language list

If your site has more than one language, create:

```text
config/language.json
```

List the language codes your site supports:

```json
{
  "languages": ["en", "fr"]
}
```

The `languages` value must be an array of language codes.

If you create `config/language.json`, the default language from `config/site.json` must be included in the list.

For example, if `defaultLanguage` is `en`, then `en` must appear in `languages`.

You do not need `config/language.json` for a one-language site.

## Translate navigation labels

After adding another language, you may also want to translate navigation labels.

That is handled by files in:

```text
config/navigation/translations/
```

See [Navigation Translations](/configuration/navigation-translations) when you are ready for that step.

## Next step

[Configure navigation translations](/configuration/navigation-translations).
