---
title: Lists
description: Create ordered, unordered, and nested lists in your documentation.
---

Lists organize information into easy-to-scan, structured formats. Mordoc inherits the support for ordered (numbered), unordered (bulleted), and nested lists.

# Unordered lists

Create bullet-point lists using `*` or `-`:

{% table %}
* Syntax
* Result
---
* 
   ```markdown
   * First item
   * Second item
   * Third item
   ```
* 
  * First item
  * Second item
  * Third item
---
{% /table %}

# Ordered lists

Create numbered lists using numbers followed by periods:

{% table %}
* Syntax
* Result
---
* 
   ```markdown
   1. First step
   2. Second step
   3. Third step
   ```
* 
  1. First step
  2. Second step
  3. Third step
---
{% /table %}

## Automatic numbering

Items are automatically numbered sequentially. You can use `1.` for all items:

{% table %}
* Syntax
* Result
---
* 
   ```markdown
   1. First item
   1. Second item (will render as 2)
   1. Third item (will render as 3)
   ```
* 
   1. First item
   1. Second item (will render as 2)
   1. Third item (will render as 3)
---
{% /table %}

This makes reordering items easier without renumbering.

{% callout type="note" %}
Starting numbers matter. If you start with `3.`, the list will begin at 3, not 1.
{% /callout %}

# Nested lists

Create hierarchical lists by indenting with tab:

## Nested unordered lists

{% table %}
* Syntax
* Result
---
* 
   ```markdown
   * Main item
   * Nested item
   * Another nested item
      * Deeply nested item
   * Another main item
   ```
* 
  * Main item
    * Nested item
    * Another nested item
      * Deeply nested item
  * Another main item
---
{% /table %}

## Nested ordered lists

{% table %}
* Syntax
* Result
---
* 
   ```markdown
   1. First step
      1. Sub-step one
      2. Sub-step two
   2. Second step
      1. Sub-step one
      2. Sub-step two
   ```
* 
  1. First step
     1. Sub-step one
     2. Sub-step two
  2. Second step
     1. Sub-step one
     2. Sub-step two
---
{% /table %}

## Mixed lists

Combine ordered and unordered lists:

{% table %}
* Syntax
* Result
---
* 
   ```markdown
   1. Main task
      * Subtask (unordered)
      * Another subtask
   2. Another main task
      * First subtask
      1. Detailed step
      2. Another detailed step
      * Second subtask
   ```
* 
  1. Main task
     - Subtask (unordered)
     - Another subtask
  2. Another main task
     - First subtask
       1. Detailed step
       2. Another detailed step
     - Second subtask
---
{% /table %}

# List items with multiple paragraphs

Add multiple paragraphs to a list item by indenting:

{% table %}
* Syntax
* Result
---
* 
   ```markdown
   1. First item with multiple paragraphs.

      This is the second paragraph for the first item. It needs to be indented.

   2. Second item.

      Another paragraph here.
   ```
* 
  1. First item with multiple paragraphs.

     This is the second paragraph for the first item. It needs to be indented.

  2. Second item.

     Another paragraph here.
---
{% /table %}

# Next steps

- [Tables](/syntax-components/tables) - Display structured data in tables
- [Code Blocks](/syntax-components/code-blocks) - Add syntax-highlighted code
- [Callouts](/syntax-components/callouts) - Create styled alert boxes

