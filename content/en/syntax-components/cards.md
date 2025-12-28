---
title: Cards & Card Grid
description: Create visual card layouts and responsive grid systems in your Mordoc documentation.
---

Cards are versatile components for displaying content in visually appealing, self-contained boxes. Use them for features, navigation, resources, or any content that benefits from visual separation.

# Single Card

Create a standalone card using Markdoc tag syntax:

```markdown
{% card title="Getting Started" %}
Learn how to create your first documentation site with Mordoc.
{% /card %}
```

Result:

{% card title="Getting Started" %}
Learn how to create your first documentation site with Mordoc.
{% /card %}

# Card with Link

Make cards clickable by adding an `href` attribute:

```markdown
{% card title="Installation Guide" href="/get-started/creating-project" %}
Step-by-step instructions for installing and setting up Mordoc.
{% /card %}
```

Result:

{% card title="Installation Guide" href="/get-started/creating-project" %}
Step-by-step instructions for installing and setting up Mordoc.
{% /card %}

When a card has an `href`, the entire card becomes clickable and interactive.

# Card with Icon

Add visual interest with icons:

```markdown
{% card title="Fast Performance" icon="/icons/speed.svg" %}
Optimized build system for quick documentation generation.
{% /card %}
```

Icon images should be placed in your project's `public/` directory and referenced with an absolute path.

# Complete Card Example

Combine title, icon, link, and description:

```markdown
{% card title="Configuration" href="/configuration/sidenav" icon="/icons/settings.svg" %}
Customize navigation, themes, and site settings to match your brand.
{% /card %}
```

# Card Attributes

{% table %}
* Attribute
* Type
* Required
* Description
---
* `title`
* string
* Yes
* Card heading
---
* `href`
* string
* No
* Makes card clickable, links to this URL
---
* `icon`
* string
* No
* Path to icon image (SVG, PNG, JPG)
{% /table %}

# Card Grid

Display multiple cards in a responsive grid layout:

```markdown
{% cardGrid cols="3" %}
{% card title="Write" icon="/icons/edit.svg" %}
Write documentation in markdown with extended syntax support.
{% /card %}

{% card title="Build" icon="/icons/build.svg" %}
Generate a static site optimized for performance and SEO.
{% /card %}

{% card title="Deploy" icon="/icons/deploy.svg" %}
Deploy anywhere - your infrastructure, your choice.
{% /card %}
{% /cardGrid %}
```

## Grid Column Options

Control the number of columns with the `cols` attribute:

{% table %}
* Columns
* Use Case
---
* `cols="2"`
* Two-column layouts
---
* `cols="3"`
* Three-column layouts (default)
---
* `cols="4"`
* Four-column layouts
{% /table %}

**Responsive Behavior:**

The grid automatically adjusts for smaller screens:
- **Mobile** (< 640px): Always 1 column
- **Tablet** (640px - 1024px): Adapts to available space
- **Desktop** (> 1024px): Uses specified `cols` value

## Card Grid Patterns

## Feature Showcase

```markdown
{% cardGrid cols="3" %}
{% card title="Markdown-First" icon="/icons/markdown.svg" %}
Write in clean, simple markdown. No complex syntax to learn.
{% /card %}

{% card title="Infrastructure Independent" icon="/icons/cloud.svg" %}
Deploy to any platform. No vendor lock-in or proprietary hosting.
{% /card %}

{% card title="Fully Customizable" icon="/icons/customize.svg" %}
Control every aspect of design with configuration files.
{% /card %}
{% /cardGrid %}
```

# Styling Cards

Customize card colors through configuration.

Edit `config/styles/main.json`:

```json
{
  "cardBorderColor": "#E6E6E6",
  "cardBorderColorDark": "#262626",
  "cardTitleColor": "#171717",
  "cardTitleColorDark": "#FAFAFA",
  "cardArrowColor": "#525252",
  "cardArrowColorDark": "#B3B3B3"
}
```

## Available Style Variables

{% table %}
* Variable
* Description
* Default
---
* `cardBorderColor`
* Card border (light mode)
* `#E6E6E6`
---
* `cardBorderColorDark`
* Card border (dark mode)
* `#262626`
---
* `cardTitleColor`
* Title color (light mode)
* `#171717`
---
* `cardTitleColorDark`
* Title color (dark mode)
* `#FAFAFA`
---
* `cardArrowColor`
* Arrow icon color (light mode)
* `#525252`
---
* `cardArrowColorDark`
* Arrow icon color (dark mode)
* `#B3B3B3`
{% /table %}

{% callout type="note" %}
These are the ONLY customizable properties for cards. Other aspects (padding, border radius, hover effects, etc.) are controlled by the design system to ensure consistency.
{% /callout %}

## Example Configurations

**Subtle Gray Cards:**

```json
{
  "cardBorderColor": "#E5E7EB",
  "cardBorderColorDark": "#374151",
  "cardTitleColor": "#111827",
  "cardTitleColorDark": "#F9FAFB",
  "cardArrowColor": "#6B7280",
  "cardArrowColorDark": "#9CA3AF"
}
```

**Blue Accent Cards:**

```json
{
  "cardBorderColor": "#DBEAFE",
  "cardBorderColorDark": "#1E3A8A",
  "cardTitleColor": "#1E40AF",
  "cardTitleColorDark": "#93C5FD",
  "cardArrowColor": "#3B82F6",
  "cardArrowColorDark": "#60A5FA"
}
```

**Green Accent Cards:**

```json
{
  "cardBorderColor": "#D1FAE5",
  "cardBorderColorDark": "#065F46",
  "cardTitleColor": "#065F46",
  "cardTitleColorDark": "#6EE7B7",
  "cardArrowColor": "#10B981",
  "cardArrowColorDark": "#34D399"
}
```

## Next Steps

- [Side Navigation](/configuration/sidenav) - Configure your site's navigation
- [Branding](/configuration/branding) - Add your logo and customize appearance
- [Build](/deployment/build) - Build your site for production
