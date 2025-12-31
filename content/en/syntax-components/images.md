---
title: Images
description: Embed images in your documentation using markdown syntax.
---

Images enhance your documentation by providing visual context, diagrams, screenshots, and illustrations. Mordoc supports standard markdown image syntax.

# Syntax

Embed images using markdown notation:

```markdown
![Alt Text](image URL)
```

**Alt Text:**

Alt text describes the image and is important for accessibility and clarity.

* Shown if the image cannot be loaded.
* Read by screen readers for accessibility.
* Used by search engines to understand the image.

# Example

{% table %}
* Syntax
* Result
---
* 
   ```markdown
   ![Artwork](/images/artwork.png)
   ```
* ![Artwork](/images/artwork.png)
---
{% /table %}

# Image paths

Images should be stored in the public/ directory and referenced using absolute paths, as shown in the example above.

```
public/
├── images/
    ├── artwork.png
    ├── flux-sail.jpg
    └── diagram.svg
```

# Next steps

* [Lists](/syntax-components/lists) - Create ordered and unordered lists
* [Tables](/syntax-components/tables) - Display structured data
* [Code Blocks](/syntax-components/code-blocks) - Add syntax-highlighted code

