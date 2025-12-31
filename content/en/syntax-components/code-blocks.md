---
title: Code Blocks
description: Display syntax-highlighted code examples in multiple programming languages in your documentation.
---

Code blocks display formatted source code with syntax highlighting, making technical documentation clear and readable. Mordoc supports code blocks in multiple programming languages.

# Inline code

For short code snippets within sentences, use single backticks:

{% table %}
* Syntax
* Result
---
* 
  ```markdown
  Use the `npm run build` to build your project.
  ``
* Use the `npm run build` to build your project.
---
{% /table %}

# Multi-line code blocks

Create code blocks using triple backticks with an optional language identifier:

{% table %}
* Syntax
* Result
---
* 
  ````markdown
  ```javascript
  function greet(name) {
    console.log(`Hello, ${name}!`);
  }
  ```
  ````
* 
  ```javascript
  function greet(name) {
    console.log(`Hello, ${name}!`);
  }
  ```
---
{% /table %}

## Next steps

- [Callouts](/syntax-components/callouts) - Create styled alert and info boxes
- [Cards](/syntax-components/cards) - Build visual card layouts
