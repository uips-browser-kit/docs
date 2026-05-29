# Markdown Style Guide

## Purpose

This guide defines the markdown conventions used across all documents in this
repository. Consistent style makes content easier to read, review, and diff.

When in doubt: prefer plain prose over decoration, structure over formatting.

## Headings

Use ATX-style headings (`#`) only. Never use Setext-style underlines.

- `#` — document title, one per file
- `##` — major sections
- `###` — subsections
- `####` — rarely; prefer restructuring the document instead

Do not skip levels. Do not use bold or italic as a substitute for a heading.
Do not add decorative punctuation to headings.

Correct:

```markdown
## Context
### Assumptions
```

Incorrect:

```markdown
**Context**
##### Deep subsection skipping levels
```

## Lists

Use `-` for all unordered lists. Never use `*` or `+`.

Use `1.` only for genuinely ordered sequences where the order and numbering
carry meaning. Do not use numbered lists for feature lists, pros/cons, or
anything where the numbers are arbitrary.

Indent nested lists with two spaces.

```markdown
- first item
- second item
  - nested item
  - nested item
- third item
```

## Emphasis

Use `**bold**` sparingly — only for a key term being introduced or a
critical warning inline in prose. Not for headings, not for decoration.

Use `_italic_` for titles of external works, technical terms on first use,
or light emphasis. Not for whole sentences.

Do not combine bold and italic (`***text***`).

## Code

Use backtick spans for inline code, file names, paths, commands, and any
literal string that should not be reformatted: `provision_org.py`, `--dry-run`.

Use fenced code blocks for multi-line code. Always specify the language:

````markdown
```python
def main():
    pass
```
````

Common language identifiers: `python`, `bash`, `yaml`, `json`, `markdown`,
`text` (for plain output with no highlighting).

## Links

Use inline links: `[label](url)`. Use reference-style links only when the
same URL appears more than twice in a document.

Link text should describe the destination, not repeat the URL.

Correct: `[contributing guide](CONTRIBUTING.md)`
Incorrect: `[click here](CONTRIBUTING.md)` or `https://github.com/...`


## Mermaid diagrams

Prefer directional relations in C4 Mermaid diagrams to reduce edge overlap.
Use `Rel_D`, `Rel_U`, `Rel_L`, and `Rel_R` instead of only `Rel` when diagrams become dense.
Keep relation labels short and avoid unnecessary cross-links.
## Tables

Use tables only for genuinely tabular data with two or more columns where
the relationship between columns matters. Do not use tables as a layout
device for lists.

Align pipes for readability in source. Include a header row.

```markdown
| Column A | Column B | Column C |
|---|---|---|
| value    | value    | value    |
```

## Horizontal Rules

Do not use horizontal rules (`---`, `***`, `___`) as section dividers.
Use headings to separate sections instead.

## Blank Lines

One blank line between paragraphs, list blocks, code blocks, and headings.
Two blank lines before a `##` section heading in long documents is acceptable
but not required.

Do not add blank lines inside a list item unless the list uses loose style
intentionally.

## Line Length

Wrap prose at 100 characters where practical. Do not wrap code blocks,
tables, or URLs. Hard wrapping is preferred over soft-wrap-only files for
clean diffs.

## File Names

Use lowercase kebab-case: `project-kickoff.md`, `adr-0001-licensing.md`.

Prefix template and meta files with an underscore: `_markdown.md`.

Prefix ADRs with a zero-padded sequence number: `0001-`, `0042-`.

## Front Matter

Use YAML front matter only when the publishing pipeline requires it.
Do not add front matter to documents that are read directly on GitHub.

## Comments

Use HTML comments for draft notes, authoring guidance, and content that
should not render. Remove comments before a document is considered final
unless they serve as permanent authoring instructions.

```markdown
<!-- TODO: fill in success metrics once baseline is established -->
```

