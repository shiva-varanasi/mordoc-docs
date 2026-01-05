---
title: Tables
description: Create rich, structured tables in your documentation.
---

Tables organize structured data into rows and columns, making information easy to scan and compare. Mordoc inherits Markdoc's table syntax which supports rich content within cells.

# Basic syntax

```
{% table %}
* Header 1
* Header 2
* Header 3
---
* Row 1, Cell 1
* Row 1, Cell 2
* Row 1, Cell 3
---
* Row 2, Cell 1
* Row 2, Cell 2
* Row 2, Cell 3
---
{% /table %}
```

**Result:**

{% table %}
* Header 1
* Header 2
* Header 3
---
* Row 1, Cell 1
* Row 1, Cell 2
* Row 1, Cell 3
---
* Row 2, Cell 1
* Row 2, Cell 2
* Row 2, Cell 3
---
{% /table %}

# Rich content in tables

The Markdoc table syntax supports rich content within cells:

## Syntax

````markdown
{% table %}
* Rich text example
* Description
---
* 
  **Code Block**
  ```javascript
  function destroyRing(fellowship) {
    if (!fellowship.includes("Frodo")) {
      throw new Error("The Ring cannot be destroyed without the Ring-bearer.");
    }
    return "The Ring is cast into Mount Doom. Middle-earth is saved.";
  }
  const fellowship = ["Frodo", "Sam", "Gandalf", "Aragorn"];
  console.log(destroyRing(fellowship));
  ```

* 
  * Checks whether the Fellowship includes Frodo.
  * Throws an error if he’s missing; otherwise returns a success message.
  * Demonstrates the function with a sample Fellowship list.
  {% callout type="note" title="Note" %}
  This is a fictional code.
  {% /callout %}
---
* 
  **Callout**
  {% callout type="danger" title="Danger" %}
  One does not simply walk into Mordor.
  {% /callout %}
* This is a danger callout
---
{% /table %}
````

## Result

{% table %}
* Rich text example
* Description
---
* 
  **Code Block**
  ```javascript
  function destroyRing(fellowship) {
    if (!fellowship.includes("Frodo")) {
      throw new Error("The Ring cannot be destroyed without the Ring-bearer.");
    }

    return "The Ring is cast into Mount Doom. Middle-earth is saved.";
  }

  const fellowship = ["Frodo", "Sam", "Gandalf", "Aragorn"];

  console.log(destroyRing(fellowship));
  ```
* 
  * Checks whether the Fellowship includes Frodo.
  * Throws an error if he’s missing; otherwise returns a success message.
  * Demonstrates the function with a sample Fellowship list.
  {% callout type="note" title="note" %}
  This is a fictional code.
  {% /callout %}
---
* 
  **Callout**
  {% callout type="danger" title="Danger" %}
  One does not simply walk into Mordor.
  {% /callout %}
* This is a danger callout
---
* 
{% /table %}

# Next steps

- [Code Blocks](/syntax-components/code-blocks) - Add syntax-highlighted code examples
- [Callouts](/syntax-components/callouts) - Create styled alert and info boxes
- [Cards](/syntax-components/cards) - Build card layouts and grids