---
title: Project Structure
description: Learn what the starter project contains and which files you will edit first.
---

A Mordoc project is just a folder on your computer. Inside that folder, some files are for your documentation content, some files are for site settings, and some files are created automatically so Mordoc can run.

You do not need to understand everything at once. This page is only a first tour of the project you created with `create-mordoc-app`.

## The folder you created

If you ran:

```bash
npx create-mordoc-app my-docs
```

Then you now have a folder named `my-docs`.

Inside it, you will see something like this:

```text
my-docs/
├── .gitignore
├── package.json
├── content/
│   └── en/
│       ├── index.md
│       ├── lore.md
│       ├── safeguards.md
│       └── wielding-the-ring.md
├── config/
│   ├── site.json
│   ├── navigation/
│   │   └── sidenav.yaml
│   ├── assets/
│   │   ├── logo.svg
│   │   └── logo-dark.svg
│   └── styles/
│       └── theme.css
├── public/
│   └── images/
│       ├── ring-og.svg
│       └── icons/
│           ├── book.svg
│           ├── shield.svg
│           └── spark.svg
├── node_modules/
└── package-lock.json
```

The starter content is fictional so you can see a working documentation site before replacing it with your own content.

## The files you will edit most

Most of your work will happen in three places:

* `content/` for the pages readers will read
* `config/` for site settings, navigation, branding, and light customization
* `public/` for images and files used by your pages

You can ignore the other generated files for now. They are explained later on this page so you know what they are when you see them.

## content

`content/` is where your documentation pages live.

In the starter project, it looks like this:

```text
content/
└── en/
    ├── index.md
    ├── lore.md
    ├── safeguards.md
    └── wielding-the-ring.md
```

Each `.md` file is a Markdown page. Markdown is the plain-text writing format you use for headings, paragraphs, lists, links, images, and Mordoc components.

The `en` folder means this content is written in English. Later, if your site has more languages, each language can have its own folder.

The starter pages become these URLs on the documentation website:

```text
content/en/index.md             -> /
content/en/lore.md              -> /lore
content/en/safeguards.md        -> /safeguards
content/en/wielding-the-ring.md -> /wielding-the-ring
```

For now, just remember this:

* Edit files in `content/en/` when you want to change page text.
* Keep `content/en/index.md`; it is the homepage for the starter site.
* Replace the fictional sample pages with your real documentation when you are ready.

Later, the [Writing Content](/writing-content/markdown-basics) section will explain Markdown, frontmatter, links, images, and Mordoc syntax in detail.

## config

`config/` is where you tell Mordoc how your documentation site should behave.

In the starter project, it looks like this:

```text
config/
├── site.json
├── navigation/
│   └── sidenav.yaml
├── assets/
│   ├── logo.svg
│   └── logo-dark.svg
└── styles/
    └── theme.css
```

You do not need to edit all of these right away. The starter project already works. Think of this folder as the place you return to when you are ready to rename the site, change navigation, replace the logo, or adjust the theme.

### site.json

`config/site.json` stores basic information about the site.

The starter file looks like this:

```json
{
  "name": "The Ring of Power",
  "description": "A field guide for keepers, scholars, and reluctant bearers of the One Ring.",
  "baseUrl": "https://ring-of-power.example.com",
  "defaultLanguage": "en"
}
```

You will eventually change the name, description, and production URL for your own documentation site.

You do not need to do that yet. You'll cover each field in detail on the [Site Configuration](/configuration/site-configuration) page.

### navigation

`config/navigation/sidenav.yaml` controls the side navigation bar links.

The starter navigation looks like this:

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

For now, notice that each visible link has two parts:

* `label` is the text readers see in the sidebar.
* `path` is the page URL.

When you add your own pages, you will update this file so readers can find them. You'll walk through that step on the [Navigation Basics](/getting-started/navigation-basics) page.

### assets

`config/assets/` is for site-level images such as the logo.

The starter project includes:

```text
config/assets/
├── logo.svg
└── logo-dark.svg
```

You can leave these alone for now. Later, you can replace them with your own logo files.

More on this in [Images and Files](/getting-started/images-and-files).

### styles

`config/styles/theme.css` is for small visual changes, such as theme colors.

You do not need to edit it while learning the basics. Mordoc already gives you a working design.

Later, [Theme CSS](/customization/basic/theme-css) will explain what is safe to customize.

## public

`public/` is for images and files used inside your documentation pages.

The starter project includes icons and an image used by the sample pages:

```text
public/
└── images/
    ├── ring-og.svg
    └── icons/
        ├── book.svg
        ├── shield.svg
        └── spark.svg
```

When a file is inside `public/`, you can reference it from a page with a path that starts with `/`.

For example:

```markdown
![Diagram](/images/diagram.png)
```

You do not need to add images yet. This will be covered later in [Images and Files](/getting-started/images-and-files).

## package.json

`package.json` is a small project information file.

You will not edit it often, but it is useful to know what it does. It stores:

* The project name
* The commands you run, such as `npm run dev` and `npm run build`
* The Mordoc version your project uses

A simplified example looks like this:

```json
{
  "name": "my-docs",
  "private": true,
  "scripts": {
    "dev": "mordoc dev",
    "build": "mordoc build"
  },
  "devDependencies": {
    "mordoc": "^1.3.0"
  }
}
```

You have already used one command from this file:

```bash
npm run dev
```

Later, when you want to update to a newer Mordoc version, you may come back to this file. For now, you can leave it as it is.

## Files you do not need to edit

Some files and folders are created automatically. It is normal to see them, but you usually do not need to open or edit them.

### node_modules

`node_modules/` contains installed packages that Mordoc needs in order to run.

You do not need to edit anything inside `node_modules/`. If it is ever missing, it can be recreated by running `npm install`.

### package-lock.json

`package-lock.json` is created by npm. It helps npm install the same package versions consistently.

You do not need to edit it by hand.

### .gitignore

`.gitignore` tells Git which generated folders should not be saved in version history.

You can leave it alone.

### dist

`dist/` is created later when you build the site:

```bash
npm run build
```

`dist/` contains the finished website files for publishing.

Do not edit files in `dist/` manually. If you need to change the site, edit the source files in `content/`, `config/`, or `public/`, then build again.

You will learn more about this later in [Build Your Site](/publishing/build-your-site).

## Next step

- [Write your first pages](/getting-started/write-pages).
