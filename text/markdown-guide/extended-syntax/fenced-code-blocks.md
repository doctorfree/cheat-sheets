---
title: Fenced Code Blocks
syntax-id: fenced-code-blocks
syntax-summary: |
  ```
  {
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
  }
  ```
---

The basic Markdown syntax allows you to create [code blocks](../basic-syntax/code.md) by indenting lines by four spaces or one tab. If you find that inconvenient, try using fenced code blocks. Use three backticks (\`\`\`) on the lines before and after the code block:

~~~~~~~~~
```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
~~~~~~~~~

The rendered output looks like this:

```text
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

**Tip:** Need to display backticks inside a code block? See [escaping characters](../basic-syntax/escaping-characters.md) to learn how to escape them.
</div>

### Syntax Highlighting

Many Markdown processors support syntax highlighting for fenced code blocks. This feature allows you to add color highlighting for whatever language your code was written in. To add syntax highlighting, specify a language next to the backticks before the fenced code block.

~~~~~~~~~
```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
~~~~~~~~~

The rendered output looks like this:

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
