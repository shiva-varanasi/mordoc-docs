---
title: Understanding Project Structure
description: Learn about the files and folders in your Mordoc project and how they work together to create your documentation site.
---

# Understanding Project Structure

A Mordoc project has a clear, organized structure that separates content, configuration, and assets. Understanding this structure helps you efficiently manage and customize your documentation.

## Project Overview

```
my-docs/
├── config/
│   ├── favicon.ico
│   ├── logo.png
│   ├── logo-dark.png
│   ├── sidenav.yaml
│   ├── site.json
│   └── styles/
│       ├── main.json
│       └── typography.json
├── content/
│   └── en/
│       ├── index.md
│       └── guides/
│           └── getting-started.md
├── public/
│   ├── images/
│   └── icons/
├── dist/
├── node_modules/
├── package.json
└── package-lock.json
```

## Directory Breakdown

### `config/` - Configuration Files

The `config/` directory contains all configuration for your documentation site.

#### Site Configuration

**`site.json`** - Global site settings:

```json
{
  "title": "My Documentation",
  "description": "Documentation for my project",
  "baseUrl": "https://docs.example.com",
  "language": "en",
  "defaultLocale": "en"
}
```

| Field | Description |
|---|---|
| `title` | Site title (appears in browser tab) |
| `description` | Meta description for SEO |
| `baseUrl` | Production URL for your documentation |
| `language` | Primary language code (e.g., "en") |

#### Navigation Configuration

**`sidenav.yaml`** - Defines your site's navigation structure. See [Side Navigation](/configuration/sidenav) for details.

#### Branding Assets

- **`logo.png`**: Logo displayed in light mode
- **`logo-dark.png`**: Logo displayed in dark mode
- **`favicon.ico`**: Browser tab icon

#### Styling Configuration

**`styles/main.json`** - Theme colors and component styles:

```json
{
  "colors": {
    "primary": "#3b82f6",
    "secondary": "#8b5cf6",
    "background": "#ffffff",
    "text": "#1f2937"
  }
}
```

**`styles/typography.json`** - Font settings and text styles:

```json
{
  "fontFamily": {
    "body": "Inter, sans-serif",
    "heading": "Inter, sans-serif",
    "code": "Monaco, monospace"
  }
}
```

{% callout type="note" %}
See the [Configuration](/configuration/branding) section for detailed customization options.
{% /callout %}

### `content/` - Documentation Content

The `content/` directory contains all your markdown documentation files, organized by language.

#### Structure

```
content/
└── en/                 # Language directory
    ├── index.md        # Homepage
    ├── guides/         # Section folder
    │   ├── intro.md
    │   └── advanced.md
    └── api/
        └── reference.md
```

#### Content Organization Rules

1. **Language Folders**: Each language gets its own folder (e.g., `en/`, `es/`, `fr/`)
2. **Homepage**: `index.md` in the language root is your site's homepage
3. **Nested Folders**: Create subdirectories to organize related content
4. **URL Mapping**: File paths become URLs:
   - `content/en/guides/intro.md` → `/guides/intro`
   - `content/en/api/reference.md` → `/api/reference`

#### Parent Pages

For parent pages with children (like "Guides" that contains multiple sub-pages):

**Option 1: Parent with Content**
```
content/en/
├── guides.md          # Parent page with content
└── guides/
    ├── intro.md       # Child page
    └── advanced.md    # Child page
```

**Option 2: Parent as Label Only**
```
content/en/
└── guides/
    ├── intro.md       # First child
    └── advanced.md    # Second child
```

In your `sidenav.yaml`, parent-only labels don't have a `path` field.

### `public/` - Static Assets

The `public/` directory holds static files that are copied directly to the build output.

```
public/
├── images/
│   ├── diagram.png
│   └── screenshot.jpg
├── icons/
│   ├── feature-1.svg
│   └── feature-2.svg
└── downloads/
    └── guide.pdf
```

#### Referencing Public Assets

In your markdown, reference these files from the root:

```markdown
![Architecture Diagram](/images/diagram.png)

{% card icon="/icons/feature-1.svg" %}
Feature description
{% /card %}

Download the [PDF guide](/downloads/guide.pdf)
```

{% callout type="warning" %}
Do not put configuration files or logos in `public/`. Branding assets belong in `config/`.
{% /callout %}

### `dist/` - Build Output

The `dist/` directory is auto-generated when you run `npm run build`. It contains the compiled static site ready for deployment.

```
dist/
├── index.html
├── guides/
│   └── intro/
│       └── index.html
├── assets/
│   ├── styles.css
│   └── main.js
└── images/
```

**Important**: Never edit files in `dist/` manually. They're regenerated on each build.

### `node_modules/` - Dependencies

Auto-generated folder containing npm packages. Don't modify or commit this to version control.

### Configuration Files

#### `package.json`

Defines your project metadata and dependencies:

```json
{
  "name": "my-docs",
  "version": "1.0.0",
  "scripts": {
    "dev": "mordoc dev",
    "build": "mordoc build",
    "preview": "mordoc preview"
  },
  "dependencies": {
    "mordoc": "^1.0.0"
  }
}
```

#### `package-lock.json`

Locks dependency versions for consistent installations. Commit this file to version control.

## File Naming Conventions

### Markdown Files

- Use lowercase letters
- Separate words with hyphens: `getting-started.md`
- Avoid spaces and special characters
- Use descriptive names: `installation-guide.md` (not `guide1.md`)

### Asset Files

- Use descriptive names: `hero-banner.png`
- Keep names URL-friendly
- Group related assets in subdirectories

## Best Practices

### Content Organization

1. **Group Related Content**: Use folders to organize topics
2. **Flat Structure**: Avoid deeply nested folders (max 2-3 levels)
3. **Consistent Naming**: Use a consistent naming pattern across files
4. **Logical Hierarchy**: Mirror your navigation structure in folders

### Version Control

Add a `.gitignore` file to exclude build artifacts:

```gitignore
node_modules/
dist/
.DS_Store
*.log
```

### Multi-Language Support

For multilingual documentation:

```
content/
├── en/
│   ├── index.md
│   └── guides/
├── es/
│   ├── index.md
│   └── guides/
└── fr/
    ├── index.md
    └── guides/
```

Each language should have identical folder structures for consistency.

## Common Workflows

### Adding a New Page

1. Create markdown file in `content/en/`
2. Add frontmatter with title and description
3. Write your content
4. Update `config/sidenav.yaml` to add navigation link
5. Save and view in development server

### Adding New Assets

1. Place files in appropriate `public/` subdirectory
2. Reference with absolute path from root: `/images/file.png`
3. Build will automatically copy to `dist/`

### Updating Styles

1. Edit `config/styles/main.json` or `typography.json`
2. Save and view changes in development server
3. Build when satisfied with results

{% callout type="note" title="Next Steps" %}
Now that you understand the structure, explore [Syntax & Components](/syntax-components/headings) to learn how to write rich documentation content.
{% /callout %}

## Troubleshooting

### Page Not Appearing

- Check file is in `content/en/` directory
- Verify file has `.md` extension
- Ensure page is added to `sidenav.yaml`
- Check for syntax errors in frontmatter

### Assets Not Loading

- Verify file exists in `public/` directory
- Check path starts with `/` (e.g., `/images/file.png`)
- Ensure filename matches exactly (case-sensitive on some platforms)
- Rebuild the site: `npm run build`

### Build Errors

- Check all markdown files have valid frontmatter
- Verify `sidenav.yaml` syntax is correct
- Ensure no circular references in navigation
- Clear `dist/` and rebuild

