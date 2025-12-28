---
title: Headings
description: Use markdown heading syntax to structure your documentation with six levels of hierarchical headings.
---

Headings create the structure and hierarchy of your documentation. Mordoc supports six levels of headings using standard markdown syntax.

# Basic Syntax

Use hash symbols (`#`) to create headings. The number of hashes determines the heading level:

```markdown
# Heading Level 1
## Heading Level 2
### Heading Level 3
#### Heading Level 4
##### Heading Level 5
###### Heading Level 6
```

# Heading Hierarchy

## Level 1: Main Heading

Use a single `#` for the main heading. 

```markdown
# Getting Started with Mordoc
```

# Getting Started with Mordoc

## Level 2: Major Sections

Use `##` for major sections within your page.

```markdown
## Installation
## Configuration
## Usage
```

## Installation
## Configuration
## Usage

## Level 3: Subsections

Use `###` for subsections under major sections.

```markdown
### System Requirements
### Download Instructions
```

### System Requirements
### Download Instructions

### Level 4-6: Detailed Hierarchy

Use `####`, `#####`, and `######` for more detailed hierarchical structures.

```markdown
#### Step-by-Step Guide
##### Prerequisites Check
###### Verify Node Version
```

#### Step-by-Step Guide
##### Prerequisites Check
###### Verify Node Version

# Best Practices

### Heading Structure Guidelines

1. **Start with Level 1** - Every page should begin with a single `#` heading
2. **Don't Skip Levels** - Go from `##` to `###`, not `##` to `####`
3. **Be Consistent** - Use parallel structure for headings at the same level
4. **Keep It Short** - Headings should be concise and descriptive
5. **Use Sentence Case** - Capitalize like a sentence, not every word

## Next Steps

Learn about other content elements:

- [Links](/syntax-components/links) - Create hyperlinks and cross-references
- [Images](/syntax-components/images) - Embed images in your documentation
- [Lists](/syntax-components/lists) - Use ordered and unordered lists
