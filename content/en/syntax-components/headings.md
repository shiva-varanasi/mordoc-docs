---
title: Headings
description: Use markdown heading syntax to structure your documentation with six levels of hierarchical headings.
---

Headings create the structure and hierarchy of your documentation. Mordoc supports six levels of headings using standard markdown syntax.

# Syntax

Use hash symbols (`#`) to create headings. The number of hashes determines the heading level:

{% table %}
* Syntax
* Result
---
*
  ```markdown
  # Heading 1

  ## Heading 2

  ### Heading 3

  #### Heading 4

  ##### Heading 5

  ###### Heading 6
  ```
* # Heading 1

  ## Heading 2

  ### Heading 3

  #### Heading 4

  ##### Heading 5

  ###### Heading 6
---
{% /table %}

# Best practices

1. **Start with Level 1** - Every page should begin with a single `#` heading
2. **Don't Skip Levels** - Go from `##` to `###`, not `##` to `####`
3. **Keep It Short** - Headings should be concise and descriptive

## Next steps

Learn about other content elements:

* [Links](/syntax-components/links) - Create hyperlinks and cross-references
* [Images](/syntax-components/images) - Embed images in your documentation
* [Lists](/syntax-components/lists) - Use ordered and unordered lists
