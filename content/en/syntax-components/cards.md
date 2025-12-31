---
title: Cards & Card Grid
description: Create visual card layouts and responsive grid systems in your documentation.
---

Cards are visually appealing, self-contained boxes that you can use for navigation within your documentation.

# Basic card syntax

A card is created using the `card` tag. At minimum, a card requires a `title` and some content.

```markdown
{% card title="Installation Guide" %}
Step-by-step instructions for installing and setting up Mordoc.
{% /card %}
```

This defines the structure of a card. Additional attributes can be added to control its behavior and appearance.

# Card attributes

{% table %}
* Attribute
* Type
* Required
* Description
---
* `title`
* string
* Yes
* Card heading text
---
* `href`
* string
* No
* Makes the card clickable and links to the specified URL
---
* `icon`
* string
* No
* Path to an icon image
---
{% /table %}

# Card with link

To use a card for navigation, add an `href` attribute. When an `href` is present, the entire card becomes clickable.

**Syntax:**

```markdown
{% card title="Installation Guide" href="/get-started/create-project" %}
Step-by-step instructions for installing and setting up Mordoc.
{% /card %}
```

**Result:**

{% card title="Installation Guide" href="/get-started/create-project" %}
Step-by-step instructions for installing and setting up Mordoc.
{% /card %}

# Card with icon

You can optionally add an icon to visually reinforce the purpose of a card.

**Syntax:**

```markdown
{% card
  title="Project structure"
  href="/get-started/project-structure"
  icon="/icons/structure.svg"
%}
Understand the project structure.
{% /card %}
```

**Result:**

{% card
  title="Project structure"
  href="/get-started/project-structure"
  icon="/icons/structure.svg"
%}
Understand the project structure.
{% /card %}

{% callout type="note" title="Note" %}
Icon images should be placed in the `public/` directory and referenced using an absolute path.
{% /callout %}

# Card grid

Use a card grid to display multiple navigation cards in a responsive layout.

**Syntax:**

```markdown
{% cardGrid cols="3" %}
{% card title="Write" href="/get-started/create-project" icon="/icons/get-started.svg" %}
Write documentation using simple Markdown syntax.
{% /card %}

{% card title="Build" href="/get-started/syntax" icon="/icons/syntax.svg" %}
Generate a static site optimized for performance.
{% /card %}

{% card title="Deploy" href="/deployment/build" icon="/icons/deployment.svg" %}
Deploy anywhere using your preferred infrastructure.
{% /card %}
{% /cardGrid %}
```

**Result:**

{% cardGrid cols="3" %}
{% card title="Write" href="/get-started/create-project" icon="/icons/get-started.svg" %}
Write documentation using simple Markdown syntax.
{% /card %}

{% card title="Build" href="/get-started/syntax" icon="/icons/syntax.svg" %}
Generate a static site optimized for performance.
{% /card %}

{% card title="Deploy" href="/deployment/build" icon="/icons/deployment.svg" %}
Deploy anywhere using your preferred infrastructure.
{% /card %}
{% /cardGrid %}

## Grid column options

Control the number of columns using the `cols` attribute:

{% table %}
* Columns
* Use case
---
* `cols="2"`
* Two-column layouts
---
* `cols="3"`
* Three-column layouts (default)
---
* `cols="4"`
* Four-column layouts
---
{% /table %}

## Responsive behavior

The card grid automatically adapts to available screen space. Cards stack on smaller screens and expand into multiple columns as more space becomes available.


# Styling cards

Mordoc provides sensible default styles for cards. If you want to customize card colors to better match your brand, you can do so by adding a `card.json` file under the `config/styles/` directory.

This file allows you to control how cards appear in both light and dark modes.

## Available style variables

{% table %}
* Variable
* Description
* Example HEX value
---
* `cardBorderColor`
* Card border color in light mode
* `#E6E6E6`
---
* `cardBorderColorDark`
* Card border color in dark mode
* `#262626`
---
* `cardTitleColor`
* Card title color in light mode
* `#171717`
---
* `cardTitleColorDark`
* Card title color in dark mode
* `#FAFAFA`
---
* `cardArrowColor`
* Arrow icon color in light mode
* `#525252`
---
* `cardArrowColorDark`
* Arrow icon color in dark mode
* `#B3B3B3`
{% /table %}

## Example configurations

**Blue accent cards:**

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

**Green accent cards:**

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
