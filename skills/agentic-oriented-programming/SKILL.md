---
name: agentic-oriented-programming
description: "Use this skill when writing or refactoring production code with coding agents. Enforces a rank-ordered doctrine: locally simple code, globally strict boundaries, narrow interfaces, dependency inversion, and invariant ownership."
---

# Agentic-Oriented Programming

Write code for a world where autonomous and semi-autonomous coding agents constantly edit systems.

Core doctrine:

- Locally simple, globally constrained.
- Prefer boring implementations inside modules.
- Enforce hard contracts at boundaries.

This skill assumes tests/specs already exist. It focuses on coding principles and architecture decisions.

## When to use

Use this skill when:

- adding new modules, services, adapters, or integration points
- refactoring architecture for maintainability under frequent AI edits
- deciding interface width, dependency direction, and ownership boundaries
- reviewing generated code for long-term operational safety

## Rank-ordered principles

Apply in this order unless the task explicitly requires otherwise.

1. **SRP + Encapsulation (invariant ownership)**
   - Each module owns one reason to change.
   - Each critical business invariant has one authoritative owner.
   - Never split the same invariant across multiple modules.

2. **Dependency Inversion (DIP) with DI at edges**
   - Domain code depends on interfaces, not vendor SDKs.
   - Wire concrete implementations in one composition root.
   - Keep model/provider/tool/framework choices at boundaries.

3. **Interface Segregation (ISP): keep interfaces small**
   - Prefer focused interfaces over wide "god" contracts.
   - Split by capability and caller need.
   - If consumers use only a subset, split the interface.

4. **Semantic DRY (single source of truth)**
   - Deduplicate business knowledge, not just syntax.
   - A rule represented in two places is a latent defect.
   - Avoid duplicate validation and policy logic across modules.

5. **KISS for internals**
   - Choose obvious, reviewable code over cleverness.
   - Prefer straightforward control flow and naming.
   - Optimize for easy regeneration and rollback.

6. **Composition over inheritance**
   - Prefer composable components and wrappers.
   - Avoid deep hierarchies that break under refactors.

7. **YAGNI + late abstraction**
   - Do not generalize before variation is proven.
   - Add extensibility only where change patterns are stable.

8. **OCP only at proven seams**
   - Use extension points where requirements are stable and recurring.
   - Avoid speculative plugin points.

## Design rules for coding agents

### Boundaries and dependency direction

- Domain layer must not import infrastructure/vendor libraries.
- Infra adapters may depend on domain interfaces, never reverse.
- Keep side effects (I/O, network, clocks, randomness) at adapters.

### Interface sizing heuristics

- Default to small interfaces with a single cohesive capability.
- Prefer multiple narrow ports over one wide manager interface.
- Use wide interfaces only for stable, external protocol facades.

### Module ownership

- Name module owners for business concepts, not technical patterns.
- Put validation and invariants where data and decisions are owned.
- If two modules write the same concept, ownership is wrong.

### Decoupling guidance

- Do not maximize decoupling blindly.
- Maximize cohesion first, then decouple at real change boundaries.
- "Easy to change independently" beats "perfectly abstract."

### Agent-friendly implementation style

- Keep functions short and intent-revealing.
- Avoid hidden control flow and magic behavior.
- Use explicit data contracts and deterministic transforms.

## Anti-patterns to reject

- direct business-layer calls to provider SDKs
- wide interfaces that mix unrelated operations
- duplicate business rules across modules
- deep inheritance trees for feature variation
- speculative abstraction without real callers
- "quick fix" patches that cross ownership boundaries

## PR review checklist

Before merge, verify all answers are "yes":

- Is there one clear owner for each changed invariant?
- Are volatile dependencies injected at module edges?
- Are interfaces as narrow as practical for current callers?
- Did this change avoid duplicating business rules?
- Is side-effectful code isolated from core logic?
- Is any new abstraction justified by current, not hypothetical, variation?

## Preferred summary phrase

Use this phrase in reviews and design docs:

"Simple internals, strict boundaries, isolated volatility."
