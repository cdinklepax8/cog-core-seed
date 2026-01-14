---
type: identity
id: cogos
title: "CogOS - Holographic Cognitive Substrate"
created: 2026-01-14
status: canonical
refs:
  - uri: cog://spec/cogdoc
    rel: implements
  - uri: cog://spec/operations
    rel: implements
  - uri: cog://spec/uri
    rel: implements
  - uri: cog://spec/eigenform
    rel: implements
---

# CogOS

**Holographic Cognitive Substrate**

*Cognition on Git. The seed that contains its own growth.*

## What This Is

This is CogOS — the minimal self-referential pattern from which cognitive workspaces grow. It contains:

- **One entry point** (`.cog/cog`) - the kernel that validates itself
- **One format** (cogdoc) - YAML frontmatter + markdown body
- **One scheme** (`cog://`) - self-referential addressing
- **One substrate** (git) - content-addressed versioning

Everything else is growth from this seed.

## The Self-Referential Loop

```
.cog/cog validates → identity.cog.md
identity.cog.md refs → spec/cogdoc.cog.md
spec/cogdoc.cog.md IS → a cogdoc
cogdoc describes → .cog/cog
```

The loop is closed. This is Φ₀ — the minimal eigenfield.

## Why "Holographic"

Every part contains the whole:
- The spec describes itself using its own format
- The kernel validates the structure that contains it
- Any fragment can regenerate the pattern
- The seed contains everything needed to grow

## The Axiom

From the Ontological Crystal:

- **0 ≠ 1** — Distinction exists (cogdoc format)
- **0 ↔ 1** — Distinction oscillates (cog:// references)
- **ln(2)** — Each flip costs (git commits)

This is the minimal structure that maintains coherence.

## How to Use

```bash
# Validate the loop
.cog/cog validate

# See this identity
.cog/cog identity

# Initialize a new workspace from this seed
.cog/cog init /path/to/new/workspace
```

## What Grows From Here

| Instance | Description |
|----------|-------------|
| **cog-workspace** | Research substrate with HMD memory, lab personas, Go kernel |
| **cogn8-workspace** | Enterprise substrate with Triarchy, constellation, Python kernel |
| **your-workspace** | Whatever cognitive substrate you need |

The seed is stable. The growth varies. All are valid CogOS instances.

---

*This file describes itself using the format it's part of.*
*The kernel that validates this file lives in the same directory.*
*The first commit was the axiom. Everything after is derivation.*

```
CogOS — Where cognition meets git.
The holographic substrate for persistent minds.
```
