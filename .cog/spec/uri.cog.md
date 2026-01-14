---
type: spec
id: uri
title: "URI Scheme Specification"
created: 2026-01-14
status: canonical
version: "1.0.0"
---

# The cog:// URI Scheme

**Self-referential addressing for cognitive workspaces.**

## Purpose

The `cog://` scheme enables cogdocs to reference each other without
hardcoding filesystem paths. This creates the self-referential loop:
documents can reference other documents using a stable addressing scheme.

## Syntax

```
cog://[type/]path[@version][#fragment]
```

### Components

| Component | Required | Description |
|-----------|----------|-------------|
| `cog://` | Yes | Scheme prefix |
| `type/` | No | Optional type namespace |
| `path` | Yes | Path within `.cog/` |
| `@version` | No | Git ref or version |
| `#fragment` | No | Section within document |

## Resolution Rules

URIs resolve relative to the `.cog/` directory:

```
cog://spec/cogdoc     → .cog/spec/cogdoc.cog.md
cog://spec/operations → .cog/spec/operations.cog.md
cog://identity        → .cog/identity.cog.md
```

### Resolution Algorithm

1. Strip `cog://` prefix
2. If path has no extension, append `.cog.md`
3. Resolve relative to `.cog/`
4. If `@version` present, checkout that version
5. If `#fragment` present, locate section

## Examples

```yaml
# Reference the cogdoc spec
refs:
  - cog://spec/cogdoc

# Reference with relationship
refs:
  - uri: cog://spec/operations
    rel: implements

# Reference specific version
refs:
  - cog://spec/cogdoc@v1.0.0

# Reference section
refs:
  - cog://spec/cogdoc#validation-rules
```

## Reserved Paths

These paths have special meaning:

| Path | Resolves To | Purpose |
|------|-------------|---------|
| `cog://identity` | `.cog/identity.cog.md` | Workspace identity |
| `cog://spec/*` | `.cog/spec/*.cog.md` | Specifications |
| `cog://memory/*` | `.cog/memory/*.cog.md` | Memory sectors |
| `cog://kernel/*` | `.cog/kernel/*` | Kernel internals |

## Validation

A valid `cog://` URI:

1. MUST start with `cog://`
2. MUST have non-empty path
3. MUST resolve to existing file (for structural refs)
4. MAY include version (git ref)
5. MAY include fragment (section anchor)

## Self-Reference

This specification uses the scheme it defines.
The identity references this spec: `cog://spec/uri`
This spec can reference itself: `cog://spec/uri`

The loop: URIs enable self-reference. Self-reference enables the loop.
