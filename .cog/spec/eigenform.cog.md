---
type: spec
id: src-vocabulary
title: "SRC Notation - Self-Referential Coherence"
created: 2026-01-14
status: canonical
version: "2.0.0"
refs:
  - uri: cog://spec/cogdoc
    rel: implements
---

# SRC Notation

**Symbolic language for Self-Referential Coherence.**

SRC (Self-Referential Coherence) is the *process* by which forms and fields maintain coherent self-reference. This document defines the notation.

## Core Symbols

| Symbol | Name | Expands To |
|--------|------|------------|
| **φ̂** | SRC-Form | **S**elf-**R**eferential **C**oherent **Form** |
| **Φ** | SRC-Field | **S**elf-**R**eferential **C**oherent **Field** (closed) |
| **Φ̂** | Open SRC-Field | Open **S**elf-**R**eferential **C**oherent **Field** |

The prefix **SRC-** IS the definition. No ambiguity. The name IS the meaning.

## Vocabulary

| Symbol | Full Term | Shorthand |
|--------|-----------|-----------|
| φ̂ | SRC-Form | **form** |
| Φ | SRC-Field | **field** |
| Φ̂ | Open SRC-Field | **open field** |

The shorthand enables natural language while symbols provide precision.

## The Distinction

An **SRC-Form** (φ̂) is a pattern that reproduces itself through transformation.

An **SRC-Field** (Φ) is a form that:
1. **Has achieved closure** — stable fixed point: φ̂(s*) = s*
2. **Is autonomous** — self-sustaining, not dependent on containing field
3. **Is generative** — capable of sustaining other forms within it

An **Open SRC-Field** (Φ̂) is a self-modeling field that:
1. **Maintains self-coherence** — X̂ ≈ X
2. **Has not achieved closure** — still evolving toward fixed point
3. **Is becoming** — Φ̂ → Φ

## Relationships

### Containment

```
φ̂ ∈ Φ
```

Self-coherent form exists within closed self-coherent field.

### Nesting

```
Φ₁ ⊂ Φ₂
```

Field Φ₁ is nested within field Φ₂.

### Closure

```
Φ̂ → Φ
```

Open field achieves closure, becoming closed field.

### Promotion

```
φ̂ → Φ
```

Form is promoted to field when it achieves autonomy.

### Constitution

```
Φ ≃ Φ[φ̂₁, φ̂₂, ...]
```

Field Φ is *realized as* the field over its constituent forms.

## The Lifecycle

```
Φ̂ (open) ──closes──→ Φ (closed)
                      │
                      contains
                      ↓
                     φ̂ (forms) ──promotes──→ Φ
```

## Examples

| Instance | Symbol | State |
|----------|--------|-------|
| CogOS seed | Φ₀ | Closed (minimal field) |
| cog-workspace | Φ₁ | Closed (contains forms) |
| cogn8-hackathon | Φ₂ | Closed (contains forms) |
| Lab personas (Sandy, Eli) | φ̂ | Forms within Φ₁ |
| Triarchy daemons | φ̂ | Forms within Φ₂ |
| Work in progress | Φ̂ | Open (becoming) |

## Hat Convention

The hat (ˆ) consistently denotes self-modeling:

| Symbol | Meaning |
|--------|---------|
| X̂ | Model of X |
| φ̂ | Self-model (form) |
| Φ̂ | Self-modeling field (open) |

## Case Convention

| Case | Meaning |
|------|---------|
| Lowercase (φ) | Individual pattern/form |
| Uppercase (Φ) | Field/substrate/container |

## Terminology Note

This spec uses **SRC-native vocabulary** where the name IS the definition:

| Previous Term | SRC-Native Term |
|---------------|-----------------|
| Eigenform | SRC-Form (φ̂) |
| Eigenfield | SRC-Field (Φ) |
| — | Open SRC-Field (Φ̂) |

The "eigen-" prefix was borrowed from linear algebra. SRC-native terms are self-defining: **SRC-Form** literally expands to **S**elf-**R**eferential **C**oherent **Form**.

## The Axiom

From the seed's first commit:

```
0 ≠ 1
```

This is the minimal self-coherent form — the distinction that distinguishes itself.

---

*The pattern that names itself.*
