# Translation Instructions

These rules apply when translating Mordoc content from the default/source language (`en`) into any other language listed in `config/language.json`. They apply equally to every target language — nothing here is specific to one language.

Read `MORDOC-SYNTAX.md` first — it defines the tag/attribute syntax and mechanics this file assumes you already know. This file only covers what to translate, what to preserve, and how to carry out a translation task; it does not repeat the tag structure itself.

## Before starting

Check `config/language.json` for the list of valid languages. `en` is the source; any other entry is a valid target.

For each file to translate, you need to know:
- **Which file(s)** — an explicit path or a clear scope (e.g. a folder).
- **Which target language.**
- **New page or update** — new means no translated file exists yet at `content/<lang>/...`; update means one already exists.

If any of this isn't clear from what the user gave you, ask. Do not assume or default silently.

## Translating a new page

Read the full English source file, then translate it in full into `content/<lang>/...` (same relative path as the English file), applying the rules below.

## Updating an existing translation

Read the full English source file and the full existing translated file. Identify which sentences or paragraphs changed in meaning since the translation was last done.

Re-translate at sentence/paragraph granularity, not word-level substitution: a small wording change in the English source can require reformulating the whole sentence or paragraph in the target language, since word order, case, and grammar rules differ by language. Check that the whole unit reads naturally in the target language rather than patching just the changed word in place.

Leave paragraphs whose English source is unchanged exactly as they are in the existing translation — this preserves established phrasing and consistency for anything you didn't need to touch.

## What to Translate vs. Preserve

| Element | Translate? |
|---|---|
| Frontmatter `title` and `description` values | Yes |
| Frontmatter `layout` value | No |
| `{% $variableName %}` | No |
| `$VARIABLE_NAME` in link targets | No |
| Tag names (`callout`, `card`, etc.) | No |
| Attribute names (`type`, `path`, `cols`, etc.) | No |
| `type` values (`note`, `tip`, `warning`, `danger`) | No |
| `path`, `icon`, `image`, `background` values | No |
| `variant` values (`primary`, `secondary`) | No |
| `cols` values | No |
| `title`, `titleAccent`, `description`, `tag` attribute values | Yes |
| `clip`/`videoEmbed` `title`, `alt` attribute values | Yes |
| `clip`/`videoEmbed` `src`, `thumbnail`, `aspectRatio` values | No |
| `accordion` `title` attribute value | Yes |
| `accordion` `defaultOpen`, `accordions` `type` values | No |
| Body text inside tags | Yes |
| Table cell text (after `*`) | Yes |
| `---` row separators in tables | No |
| Standard Markdown text (paragraphs, headings, lists) | Yes |
| Code blocks (fenced with ` ``` `) | No — preserve verbatim |
| `sequence-diagram` blocks — `"<label>"` after `as`, message text after `:`, `# comment` text | Yes |
| `sequence-diagram` blocks — language tag, `actor`/`as` keywords, `<id>` values, `icon=<path>`, arrow syntax, `\n` markers | No |
| Inline code (backtick `code`) | No — preserve verbatim |
| Link paths `[text](/path)` — the path part | No |
| Link paths `[text](/path)` — the text part | Yes |
| Navigation `label` values | Yes — in `config/navigation/translations/<lang>.yaml` |
| Navigation `path`, `sidenav`, `variant`, `expanded` values | No |
| Footer lines (`config/navigation/footer.yaml`) | Yes — in `config/navigation/translations/<lang>.yaml`, see Footer Line Translations below |
| Site chrome/UI strings (search box, aria-labels, "On this page", etc.) | No — automatically translated, not user-authored; out of scope for content translation |

## Path Prefixing

When translating content for a non-default language folder `content/<lang>/`, all relative navigation link paths must be prefixed with the language code:

- Markdown link paths: `[text](/some/page)` → `[text](/<lang>/some/page)`
- `path` attributes in Mordoc tags: `path="/some/page"` → `path="/<lang>/some/page"`

Do **not** prefix asset paths — images, icons, and backgrounds are shared across all languages:
- `icon="/icons/..."`, `image="/images/..."`, `background="/images/..."` — leave as-is.

Do **not** prefix paths inside code blocks (fenced with ` ``` `) — preserve them verbatim.

## Navigation Label Translations

Navigation labels (see `MORDOC-SYNTAX.md` for which files contain them: `sidenav.yaml`, `topnav.yaml`, `headernav.yaml`, custom per-area sidenav files) are translated separately from content files, in one flat YAML file per language:

```text
config/navigation/translations/<lang>.yaml
```

Syntax — original label on the left, translated label on the right:

```yaml
Getting Started: Premiers pas
Writing Content: Rediger du contenu
Configuration: Configuration
```

Translate every `label` value from every navigation file into this translation file. Do not translate `path`, `sidenav` (filename references), `variant`, or `expanded` values. If a label is missing from the translation file, Mordoc falls back to showing the original label.

## Footer Line Translations

Lines from `config/navigation/footer.yaml` (see `MORDOC-SYNTAX.md`) are translated in the same flat file as navigation labels, `config/navigation/translations/<lang>.yaml` — key on the literal English line (link syntax included), value the translated line:

```yaml
"Powered by [Mordoc](https://mordoc.dev)": "Bereitgestellt von [Mordoc](https://mordoc.dev)"
"[Privacy policy](/privacy)": "[Datenschutzrichtlinie](/privacy)"
```

Quote both sides when the line contains `[text](url)` link syntax — an unquoted leading `[` reads as a YAML list, same reasoning as `footer.yaml` itself (see `MORDOC-SYNTAX.md`). Translate the visible text, keep the link syntax intact.

Unlike sidenav/topnav paths (which Mordoc prefixes with the language code automatically at render time), a footer line's path is part of the translated string itself and is **not** auto-prefixed — apply Path Prefixing (above) by hand when the link is internal:

```yaml
"[Privacy policy](/privacy)": "[Politique de confidentialité](/fr/privacy)"
```

External links (`http://`, `https://`, `//`) are left as-is, same as elsewhere. If a footer line is missing from the translation file, Mordoc falls back to showing the original (English) line.

## Site Chrome / UI Strings

Mordoc's own interface text — the search box, sidebar/menu aria-labels, "On this page", breadcrumb "Home", copy-link tooltips, and similar strings the reader didn't author — is translated automatically by Mordoc itself for its built-in languages, separately from content translation. There is nothing to translate or configure for these: no file to edit, no override mechanism. Do not create or edit anything for this; it's out of scope for a content translation task.
