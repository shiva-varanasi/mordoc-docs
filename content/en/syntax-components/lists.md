---
title: Lists
description: Create ordered, unordered, and nested lists in your Mordoc documentation using markdown syntax.
---

# Lists

Lists organize information into easy-to-scan, structured formats. Mordoc supports ordered (numbered), unordered (bulleted), and nested lists.

## Unordered Lists

Create bullet-point lists using `-`, `*`, or `+`:

```markdown
- First item
- Second item
- Third item
```

Result:

- First item
- Second item
- Third item

### Alternative Markers

All three markers produce identical output:

```markdown
- Item with dash
* Item with asterisk
+ Item with plus
```

Choose one style and be consistent throughout your documentation.

## Ordered Lists

Create numbered lists using numbers followed by periods:

```markdown
1. First step
2. Second step
3. Third step
```

Result:

1. First step
2. Second step
3. Third step

### Automatic Numbering

Markdown automatically numbers items sequentially. You can use `1.` for all items:

```markdown
1. First item
1. Second item (will render as 2)
1. Third item (will render as 3)
```

This makes reordering items easier without renumbering.

{% callout type="note" %}
Starting numbers matter. If you start with `3.`, the list will begin at 3, not 1.
{% /callout %}

## Nested Lists

Create hierarchical lists by indenting with 2-4 spaces or one tab:

### Nested Unordered Lists

```markdown
- Main item
  - Nested item
  - Another nested item
    - Deeply nested item
- Another main item
```

Result:

- Main item
  - Nested item
  - Another nested item
    - Deeply nested item
- Another main item

### Nested Ordered Lists

```markdown
1. First step
   1. Sub-step one
   2. Sub-step two
2. Second step
   1. Sub-step one
   2. Sub-step two
```

Result:

1. First step
   1. Sub-step one
   2. Sub-step two
2. Second step
   1. Sub-step one
   2. Sub-step two

### Mixed Lists

Combine ordered and unordered lists:

```markdown
1. Main task
   - Subtask (unordered)
   - Another subtask
2. Another main task
   - First subtask
     1. Detailed step
     2. Another detailed step
   - Second subtask
```

Result:

1. Main task
   - Subtask (unordered)
   - Another subtask
2. Another main task
   - First subtask
     1. Detailed step
     2. Another detailed step
   - Second subtask

## List Items with Multiple Paragraphs

Add multiple paragraphs to a list item by indenting:

```markdown
1. First item with multiple paragraphs.

   This is the second paragraph for the first item. It needs to be indented.

2. Second item.

   Another paragraph here.
```

Result:

1. First item with multiple paragraphs.

   This is the second paragraph for the first item. It needs to be indented.

2. Second item.

   Another paragraph here.

## Lists with Code Blocks

Include code blocks in list items:

```markdown
1. Install the package:

   ```bash
   npm install mordoc
   ```

2. Configure your project:

   ```json
   {
     "title": "My Docs"
   }
   ```
```

Result:

1. Install the package:

   ```bash
   npm install mordoc
   ```

2. Configure your project:

   ```json
   {
     "title": "My Docs"
   }
   ```

## Lists with Other Elements

### Lists with Links

```markdown
- [Installation Guide](/get-started/creating-project)
- [Configuration Reference](/configuration/sidenav)
- [Deployment Instructions](/deployment/build)
```

Result:

- [Installation Guide](/get-started/creating-project)
- [Configuration Reference](/configuration/sidenav)
- [Deployment Instructions](/deployment/build)

### Lists with Emphasis

```markdown
- **Bold item**: Description here
- *Italic item*: Another description
- `Code item`: Technical term
```

Result:

- **Bold item**: Description here
- *Italic item*: Another description
- `Code item`: Technical term

### Lists with Images

```markdown
1. First step:
   
   ![Screenshot](/images/step1.png)

2. Second step:
   
   ![Screenshot](/images/step2.png)
```

## Task Lists

Create checkboxes with task list syntax:

```markdown
- [ ] Incomplete task
- [x] Completed task
- [ ] Another incomplete task
```

Result:

- [ ] Incomplete task
- [x] Completed task
- [ ] Another incomplete task

{% callout type="note" title="Interactive Checkboxes" %}
Task lists render as checkboxes in the documentation. They're perfect for checklists, prerequisites, and progress tracking.
{% /callout %}

## Next Steps

- [Tables](/syntax-components/tables) - Display structured data in tables
- [Code Blocks](/syntax-components/code-blocks) - Add syntax-highlighted code
- [Callouts](/syntax-components/callouts) - Create styled alert boxes

