---
title: Branding
description: Customize your Mordoc documentation with logos, favicons, and typography to match your brand.
---

Personalize your documentation site with custom logos, favicons, and typography to match your brand identity.

# Logo

Add your logo to display in the site header and navigation.

## Logo Files

Place logo files in the `config/` directory. Mordoc automatically detects and uses them:

```
config/
├── logo.png          # Light mode logo
├── logo-dark.png     # Dark mode logo (optional)
└── favicon.ico       # Site favicon
```

## Supported Formats

Mordoc checks for logo files in this order of preference:

1. **SVG** - `logo.svg` (best for scalability)
2. **PNG** - `logo.png` (best for photos/gradients)
3. **JPG** - `logo.jpg` (alternative format)
4. **JPEG** - `logo.jpeg` (alternative format)

The first format found is used automatically.

## Light and Dark Mode Logos

Provide separate logos optimized for light and dark themes:

- `logo.svg` or `logo.png` - Displayed in light mode
- `logo-dark.svg` or `logo-dark.png` - Displayed in dark mode

If only a light mode logo is provided, it will be used in both themes.

{% callout type="note" %}
Dark mode detection is automatic based on system preferences. No configuration needed.
{% /callout %}

## Logo Recommendations

{% table %}
* Property
* Recommendation
---
* Format
* SVG preferred for logos with text/icons, PNG for complex images
---
* Dimensions
* Width: 120-200px, Height: 32-48px
---
* Background
* Transparent (for PNG/SVG)
---
* Resolution
* 2x for retina displays (if using PNG)
{% /table %}

# Favicon

The favicon appears in browser tabs, bookmarks, and browser history.

## Favicon File

Place your favicon in the `config/` directory:

```
config/
└── favicon.ico
```

Mordoc automatically detects and uses `favicon.ico` if present.

## Favicon Format

**Recommended: ICO format**

Use a multi-size ICO file containing:
- 16×16 pixels
- 32×32 pixels
- 48×48 pixels (optional)

This ensures proper display across all browsers and contexts.

## Creating a Favicon

**From an image file:**

1. Create a 32×32 or 48×48 pixel image
2. Export as PNG
3. Convert to ICO format using a tool like:
   - [favicon.io](https://favicon.io)
   - [RealFaviconGenerator](https://realfavicongenerator.net)
   - ImageMagick: `convert icon.png favicon.ico`

# Typography

Customize the fonts used throughout your documentation.

## Font Configuration

Edit `config/styles/typography.json`:

```json
{
  "fontFamilyBase": "Inter, system-ui, -apple-system, sans-serif",
  "fontFamilyHeading": "Inter, system-ui, -apple-system, sans-serif",
  "fontFamilyMono": "Monaco, 'Courier New', monospace"
}
```

## Available Typography Variables

{% table %}
* Variable
* Description
* Default
---
* `fontFamilyBase`
* Body text font
* `"Inter", system-ui, sans-serif`
---
* `fontFamilyHeading`
* Headings font
* `"Inter", system-ui, sans-serif`
---
* `fontFamilyMono`
* Code and monospace font
* `"SF Mono", Monaco, monospace`
{% /table %}

## Font Stack Best Practices

Always include fallback fonts:

```json
{
  "fontFamilyBase": "Your Custom Font, system-ui, -apple-system, BlinkMacSystemFont, sans-serif",
  "fontFamilyMono": "Your Mono Font, Monaco, Consolas, monospace"
}
```

This ensures text displays properly while custom fonts load, or if they fail to load.

## Using System Fonts

For optimal performance, use system fonts:

```json
{
  "fontFamilyBase": "system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif",
  "fontFamilyHeading": "system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif",
  "fontFamilyMono": "ui-monospace, Monaco, 'Cascadia Code', monospace"
}
```

**Benefits:**
- Zero loading time
- Native OS appearance
- Excellent performance
- No external dependencies

## Using Web Fonts

To use custom web fonts, you'll need to add them to your project.

**Option 1: Google Fonts**

Add Google Fonts link to your HTML (requires template customization):

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;600;700&display=swap">
```

Then reference in typography.json:

```json
{
  "fontFamilyBase": "Roboto, sans-serif"
}
```

**Option 2: Self-Hosted Fonts**

Place font files in `public/fonts/` directory and create a CSS file that defines `@font-face` rules. Reference the fonts in typography.json.

{% callout type="warning" %}
Custom font loading requires additional setup beyond configuration files. The typography.json file only sets font family names that should already be available.
{% /callout %}

# Link Colors

Customize link appearance throughout your documentation.

Edit `config/styles/typography.json`:

```json
{
  "linkColor": "#0665c4",
  "linkColorDark": "#0665c4",
  "linkHoverColor": "#0a0b66",
  "linkHoverColorDark": "#61b1f2"
}
```

## Available Link Variables

{% table %}
* Variable
* Description
* Default
---
* `linkColor`
* Link color in light mode
* `#171717`
---
* `linkColorDark`
* Link color in dark mode
* `#fafafa`
---
* `linkHoverColor`
* Link hover color in light mode
* `#000000`
---
* `linkHoverColorDark`
* Link hover color in dark mode
* `#FFFFFF`
{% /table %}

{% callout type="note" %}
These are the ONLY customizable properties for links. Other link styling (underlines, font weight, etc.) is controlled by the design system to ensure consistency.
{% /callout %}

# Site Metadata

Configure your site's basic information in `config/site.json`:

```json
{
  "title": "My Documentation",
  "description": "Comprehensive documentation for My Product",
  "keywords": ["documentation", "guide", "api"],
  "baseUrl": "https://docs.example.com"
}
```

## Metadata Properties

{% table %}
* Property
* Description
* Required
---
* `title`
* Site title (appears in browser tab, navigation)
* Yes
---
* `description`
* Site description (for SEO)
* No
---
* `keywords`
* Array of keywords (for SEO)
* No
---
* `baseUrl`
* Full URL of your site
* No
{% /table %}

This metadata is used for:
- Browser page titles
- SEO meta tags
- Social media sharing
- Navigation elements

# Complete Branding Example

Here's a complete branding setup:

**File Structure:**

```
config/
├── logo.svg
├── logo-dark.svg
├── favicon.ico
├── site.json
└── styles/
    └── typography.json
```

**config/site.json:**

```json
{
  "title": "Acme Documentation",
  "description": "Official documentation for Acme products and services",
  "baseUrl": "https://docs.acme.com",
  "keywords": ["acme", "documentation", "api", "guide"]
}
```

**config/styles/typography.json:**

```json
{
  "fontFamilyBase": "system-ui, -apple-system, sans-serif",
  "fontFamilyHeading": "system-ui, -apple-system, sans-serif",
  "fontFamilyMono": "Monaco, Consolas, monospace",
  "linkColor": "#2563eb",
  "linkColorDark": "#60a5fa",
  "linkHoverColor": "#1e40af",
  "linkHoverColorDark": "#93c5fd"
}
```

# Next Steps

- [Side Navigation](/configuration/sidenav) - Configure navigation structure
- [Build](/deployment/build) - Build your branded documentation site
- [Preview](/deployment/preview) - Test your branding locally
