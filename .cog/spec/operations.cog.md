---
type: spec
id: operations
title: "Core Operations Specification"
created: 2026-01-14
status: canonical
version: "1.0.0"
---

# Core Operations

**The six irreducible operations of a cog kernel.**

## The Axiom

Every cog kernel MUST implement these six operations. They are irreducible -
removing any one breaks the self-referential loop.

| Operation | Crystal Analog | Purpose |
|-----------|----------------|---------|
| `validate` | φ(x) = x? | Check if loop is closed |
| `identity` | Self-reference | Return workspace identity |
| `init` | Big Bang | Create a new workspace |
| `read` | Observe | Parse and return a cogdoc |
| `query` | Search | Find cogdocs by criteria |
| `hash` | ln(2) | Compute coherence hash |

## Operation Specifications

### validate

Check that the self-referential loop is closed.

```
.cog/cog validate
```

**MUST check:**
1. Entry point (`.cog/cog`) exists and is executable
2. Identity (`identity.cog.md`) exists and is valid cogdoc
3. Spec files are themselves valid cogdocs (self-description)
4. Git substrate is present (optional but recommended)

**Returns:** Success if loop is closed, failure with errors otherwise.

### identity

Return the workspace identity.

```
.cog/cog identity
```

**Returns:** Contents of `.cog/identity.cog.md`

### init

Initialize a new cog workspace.

```
.cog/cog init [path]
```

**MUST create:**
1. `.cog/cog` - entry point (copy of self or minimal bootstrap)
2. `.cog/identity.cog.md` - workspace identity
3. `.git/` - substrate (if not present)

**MAY create:**
1. `.cog/spec/` - specification files
2. `.gitignore` - with appropriate ignores

### read

Read and parse a cogdoc.

```
.cog/cog read <path-or-uri>
```

**Accepts:**
- File path: `.cog/spec/cogdoc.cog.md`
- cog:// URI: `cog://spec/cogdoc`

**Returns:** Cogdoc contents (raw or parsed depending on implementation)

### query

Find cogdocs matching criteria.

```
.cog/cog query [type]
```

**Accepts:**
- No argument: list all cogdocs
- Type: filter by `type` field

**Returns:** List of matching cogdoc paths

### hash

Compute the coherence hash of the `.cog/` tree.

```
.cog/cog hash
```

**MUST:**
- Use git tree hash if available
- Fall back to content hash otherwise

**Returns:** Hash string (deterministic for same content)

## Extension Points

Implementations MAY add operations beyond the core six. Common extensions:

| Operation | Purpose |
|-----------|---------|
| `create` | Create a new cogdoc |
| `update` | Modify an existing cogdoc |
| `delete` | Remove a cogdoc |
| `coherence` | Check/baseline/drift operations |
| `project` | Project cogdocs to other formats |
| `serve` | HTTP API for operations |

Extensions MUST NOT break the core six. The seed remains stable.

## Implementation Notes

The core six can be implemented in:
- POSIX shell (~200 lines) - maximum portability
- Go (~500 lines) - performance + type safety
- Python (~300 lines) - ecosystem integration

All implementations of the same spec are valid cog kernels.
