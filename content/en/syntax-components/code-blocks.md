---
title: Code Blocks
description: Display syntax-highlighted code examples in multiple programming languages in your Mordoc documentation.
---

Code blocks display formatted source code with syntax highlighting, making technical documentation clear and readable. Mordoc supports code blocks in multiple programming languages powered by Prism.js.

# Inline Code

For short code snippets within sentences, use single backticks:

```markdown
Use the `npm install` command to install dependencies.
```

Result: Use the `npm install` command to install dependencies.

## When to Use Inline Code

- Variable names: `userName`
- Function names: `calculateTotal()`
- File names: `config.json`
- Command names: `git commit`
- Short code snippets: `const x = 10`
- CSS classes: `.button-primary`
- HTML tags: `<div>`

# Multi-Line Code Blocks

Create code blocks using triple backticks with an optional language identifier:

````markdown
```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}
```
````

Result:

```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}
```

The language identifier enables syntax highlighting appropriate for that language.

# Language-Specific Syntax Highlighting

Specify the programming language for appropriate syntax highlighting:

## JavaScript

````markdown
```javascript
const fetchData = async (url) => {
  const response = await fetch(url);
  return response.json();
};
```
````

```javascript
const fetchData = async (url) => {
  const response = await fetch(url);
  return response.json();
};
```

## TypeScript

````markdown
```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

function getUser(id: number): Promise<User> {
  return fetch(`/api/users/${id}`).then(res => res.json());
}
```
````

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

function getUser(id: number): Promise<User> {
  return fetch(`/api/users/${id}`).then(res => res.json());
}
```

## Next Steps

- [Callouts](/syntax-components/callouts) - Create styled alert and info boxes
- [Cards](/syntax-components/cards) - Build visual card layouts
- [Tables](/syntax-components/tables) - Display tabular data
