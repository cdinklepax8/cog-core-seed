---
type: spec
id: cogdoc
title: "Cogdoc Format Specification"
created: 2026-01-14
status: canonical
version: "1.0.0"
---

# Cogdoc Format

**The atomic unit of cognitive workspaces.**

A cogdoc is a self-describing document: YAML frontmatter + markdown body.

## Structure

```
---
type: <type>
id: <identifier>
[additional fields...]
refs:
  - <uri>
  - uri: <uri>
    rel: <relationship>
---

# Title

Markdown body content.
```

## Required Fields

| Field | Type | Description |
|-------|------|-------------|
| `type` | string | Document type (identity, spec, insight, task, etc.) |
| `id` | string | Unique identifier within type |

## Optional Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Human-readable title |
| `created` | date | Creation date (YYYY-MM-DD) |
| `status` | string | Lifecycle status (draft, active, canonical, archived) |
| `version` | string | Semantic version |
| `refs` | array | References to other cogdocs |

## Reference Format

References can be simple or typed:

```yaml
# Simple (implies rel: refs)
refs:
  - cog://spec/uri
  - cog://spec/cogdoc

# Typed (explicit relationship)
refs:
  - uri: cog://spec/operations
    rel: implements
  - uri: cog://spec/cogdoc
    rel: extends
```

### Relationship Types

| Relation | Meaning |
|----------|---------|
| `refs` | Generic reference (default) |
| `implements` | This implements the referenced spec |
| `extends` | This extends the referenced document |
| `supersedes` | This replaces the referenced document |
| `describes` | This describes the referenced entity |
| `requires` | This depends on the referenced document |

## Validation Rules

1. File MUST begin with `---` (YAML frontmatter delimiter)
2. Frontmatter MUST be valid YAML
3. `type` field MUST be present
4. `id` field MUST be present
5. If `refs` present, each MUST resolve via cog:// scheme
6. Body MUST be valid markdown

## File Naming

Cogdocs use the `.cog.md` extension:

```
identity.cog.md
spec/cogdoc.cog.md
memory/semantic/insights/some-insight.cog.md
```

## Self-Reference

This specification is itself a cogdoc. It uses the format it describes.
The kernel validates this file using the rules defined within it.

The loop: cogdoc.cog.md describes cogdocs, and IS a cogdoc.
