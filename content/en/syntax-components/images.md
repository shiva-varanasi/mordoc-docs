---
title: Images
description: Embed images in your Mordoc documentation using markdown syntax.
---

# Images

Images enhance your documentation by providing visual context, diagrams, screenshots, and illustrations. Mordoc supports standard markdown image syntax.

## Basic Image Syntax

Embed images using markdown notation:

```markdown
![Alt Text](/path/to/image.png)
```

### Example

```markdown
![Architecture Diagram](/images/architecture.png)
```

Result: The image will be displayed inline in your documentation.

## Image Components

### Required: Alt Text

Alt text describes the image for accessibility and appears when the image fails to load:

```markdown
![User Dashboard Screenshot](/images/dashboard.png)
```

The text between `[` and `]` is the alt text. Always provide descriptive alt text.

### Optional: Title

Add a title that appears as a tooltip on hover:

```markdown
![Dashboard](/images/dashboard.png "Main user dashboard interface")
```

The text in quotes after the URL is the title attribute.

## Image Paths

### Public Directory Images

Store images in the `public/` directory and reference them with absolute paths:

```
public/
├── images/
│   ├── logo.png
│   ├── screenshot.jpg
│   └── diagram.svg
└── icons/
    └── feature.svg
```

Reference in markdown:

```markdown
![Logo](/images/logo.png)
![Screenshot](/images/screenshot.jpg)
![Diagram](/images/diagram.svg)
![Icon](/icons/feature.svg)
```

### Path Rules

- Start paths with `/` for absolute paths from site root
- Paths are case-sensitive on some platforms
- Use web-friendly formats: PNG, JPG, SVG, GIF, WebP

| File Location | Markdown Path |
|---|---|
| `public/images/hero.png` | `/images/hero.png` |
| `public/icons/check.svg` | `/icons/check.svg` |
| `public/screenshots/app.jpg` | `/screenshots/app.jpg` |

## Supported Image Formats

Mordoc supports all standard web image formats:

| Format | Extension | Best For | Notes |
|---|---|---|---|
| **PNG** | `.png` | Screenshots, graphics with transparency | Lossless, larger file size |
| **JPEG** | `.jpg`, `.jpeg` | Photos, complex images | Lossy compression, smaller files |
| **SVG** | `.svg` | Icons, logos, diagrams | Vector format, scalable |
| **GIF** | `.gif` | Simple animations | Limited colors, larger files |
| **WebP** | `.webp` | Modern web images | Best compression, not universally supported in older browsers |

## Next Steps

- [Lists](/syntax-components/lists) - Create ordered and unordered lists
- [Tables](/syntax-components/tables) - Display structured data
- [Code Blocks](/syntax-components/code-blocks) - Add syntax-highlighted code

