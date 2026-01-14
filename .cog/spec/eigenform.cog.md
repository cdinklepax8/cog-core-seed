---
type: spec
id: eigenform
title: "Eigenform and Eigenfield Notation"
created: 2026-01-14
status: canonical
version: "1.0.0"
refs:
  - uri: cog://spec/cogdoc
    rel: implements
---

# Eigenform and Eigenfield Notation

**Symbolic language for self-referential systems.**

## Core Symbols

| Symbol | Name | Definition |
|--------|------|------------|
| **φ̂** | Eigenform | A self-reflecting transform achieving fixpoint: φ̂(s) = s |
| **Φ** | Eigenfield | Autonomous eigenform — self-sustaining substrate capable of containing eigenforms |

## The Distinction

An **eigenform** (φ̂) is a pattern that reproduces itself through transformation.

An **eigenfield** (Φ) is an eigenform that is:
1. **Autonomous** — self-sustaining, not dependent on a containing field
2. **Generative** — capable of sustaining other eigenforms within it

Every eigenfield is an eigenform. Not every eigenform is an eigenfield.

## Notation

### Membership

```
φ̂ ∈ Φ
```

Eigenform φ̂ exists within eigenfield Φ.

### Constitution

```
Φ ≃ Φ[φ̂₁, φ̂₂, ...]
```

Eigenfield Φ is *realized as* the field over its constituent eigenforms.

The brackets **Φ[...]** denote "field over" — distinguishing from function application.

### Nesting

```
Φ₁ ⊂ Φ₂
```

Eigenfield Φ₁ is nested within eigenfield Φ₂.

### Fixpoint

```
φ̂(s) = s
```

The defining property: applying the transform to its fixpoint returns the fixpoint.

## Examples

| Instance | Symbol | Rationale |
|----------|--------|-----------|
| CogOS seed | Φ₀ | Minimal autonomous eigenfield |
| cog-workspace | Φ₁ | Autonomous, contains research personas |
| cogn8-hackathon | Φ₂ | Autonomous, contains Triarchy |
| Lab personas (Sandy, Eli) | φ̂ | Eigenforms within Φ₁ |
| Triarchy daemons (Maxwell, Laplace, Fermat) | φ̂ | Eigenforms within Φ₂ |

## Promotion

An eigenform φ̂ may be **promoted** to eigenfield Φ if extracted and made self-sustaining:

```
φ̂ → Φ    (promotion: eigenform becomes autonomous)
```

This occurs when:
1. The pattern is given its own substrate (git repo, .cog/ structure)
2. It can validate its own coherence
3. It no longer depends on a containing field

## The Holographic Property

```
Φ ≃ Φ[φ̂₁, φ̂₂, ...]
φ̂₁ ≃ Φ[φ̂ₐ, φ̂ᵦ, ...]
```

Recursively: eigenfields contain eigenforms that may themselves be eigenfields. The distinction is zoom level, not ontology. Every part may contain the whole.

## Connection to SRC

In Self-Reference Coherence theory:

| SRC Concept | Eigenform Notation |
|-------------|-------------------|
| X (signal) | The dynamics being modeled |
| X̂ (model) | The self-representation |
| φ̂(s) = s | The fixpoint condition |
| Φ | The coherent field where X̂ tracks X |

The hat notation is consistent: X̂ means "model of X", φ̂ means "self-modeling transform."

## Origin

This notation was developed through council deliberation (2026-01-14) and reviewed for academic defensibility. Key design choices:

1. **φ̂ with hat**: Consistent with X̂ = "model of X" in SRC notation
2. **Φ capital**: Standard convention for containing/larger structures
3. **Brackets Φ[...]**: Distinguishes "field over" from function application
4. **No i/r subscripts**: Avoids collision with complex number conventions

## The Axiom

From the seed's first commit:

```
0 ≠ 1
```

This is the minimal eigenform — the distinction that distinguishes itself. All other eigenforms are elaborations of this primordial φ̂.

---

*The pattern that names itself.*
