---
title: Variables
description: Define reusable text values for your Mordoc content.
---

Variables let you write a value once and reuse it in many pages.

They are useful for names, versions, URLs, support addresses, or other small pieces of text that may change later.

## Create the variables file

Variables live in this optional file:

```text
config/variables.yaml
```

Create it only when you have values you want to reuse.

## Add a variable

Start with a simple name and value:

```yaml
productName: Acme
supportEmail: support@example.com
currentVersion: "1.0"
```

Use names that describe what the value means.

Plain values such as names, emails, and simple URLs usually do not need quotes.

Use quotes when a value should stay as text but looks like a number, or when it contains characters YAML may treat in a special way.

## Use a variable in content

After a variable is defined, you can use it in Markdown content:

```markdown
Welcome to {% $productName %}.
```

Mordoc replaces the variable with the value from `config/variables.yaml`.

With this variable:

```yaml
productName: Acme
```

Readers see:

```text
Welcome to Acme.
```

## Use variables for repeated values

Variables are most helpful when the same value appears in several places.

For example:

```yaml
supportEmail: support@example.com
```

Then use it wherever readers need the support address:

```markdown
Email {% $supportEmail %} if you need help.
```

If the address changes later, you only need to update `config/variables.yaml`.

## Use variables in links

Variables can also be used as link targets.

For links, write the variable directly in the parentheses:

```markdown
[Contact support]($SUPPORT_PORTAL_URL)
```

Do not use curly braces in a link target:

```markdown
[Contact support]({{ $SUPPORT_PORTAL_URL }})
```

The link variable should be defined in `config/variables.yaml`:

```yaml
SUPPORT_PORTAL_URL: https://support.example.com
```

## Keep variables simple

Variables work best for short text values.

Good examples:

* Product names
* Version numbers
* Support email addresses
* Common website URLs

Avoid using variables for long paragraphs. Long content is usually clearer when it stays directly in the page.

## Next step

[Configure assets and branding](/configuration/assets-and-branding).
