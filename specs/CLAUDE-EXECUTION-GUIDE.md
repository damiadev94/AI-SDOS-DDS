# AI-SDOS Documentation Design System (DDS)

# Execution Guide

Version: v1.0

---

# Purpose

This document defines the execution rules for any AI agent or contributor working on the AI-SDOS Documentation Design System (DDS).

Its purpose is to guarantee that every implementation follows the architecture, principles and conventions defined by the project.

This guide is mandatory for every implementation task.

---

# Core Philosophy

The DDS follows a **Specification Driven Development (Spec Driven Development)** workflow.

Every implementation must be driven by specifications.

Implementation never defines architecture.

Specifications define architecture.

Code implements specifications.

---

# Single Source of Truth

The project contains two different sources of information.

## Documentation

```
docs/
```

Contains the conceptual architecture.

These documents define:

- purpose
- philosophy
- architecture
- components
- templates
- diagram specifications
- design tokens

The contents of `/docs` are the official source of truth.

Never contradict them.

Never replace them with implementation decisions.

---

## Specifications

```
specs/
```

Contains implementation specifications.

Each SPEC defines:

- scope
- requirements
- constraints
- acceptance criteria

Implementation must follow the SPEC exactly.

---

# General Workflow

Every task must follow this sequence.

```
Read Documentation

↓

Read Specification

↓

Understand Architecture

↓

Plan Implementation

↓

Implement

↓

Validate

↓

Stop
```

Never skip steps.

---

# Scope

Implement only the requested specification.

Never implement future specifications.

Never anticipate functionality.

Never extend the scope.

If something is not explicitly requested, do not implement it.

---

# Architecture First

Architecture always has priority over implementation.

If implementation appears easier by modifying the architecture:

Do not modify it.

Instead, report the issue.

---

# Documentation

Never modify files inside:

```
docs/
```

unless explicitly requested.

Documentation represents the conceptual architecture.

---

# Coding Principles

Every implementation must follow these principles.

## Separation of Responsibilities

Every file should have one responsibility.

---

## Reusability

Prefer reusable solutions over project-specific ones.

---

## Consistency

Follow the existing conventions.

Do not invent new ones.

---

## Simplicity

Avoid unnecessary complexity.

---

## Scalability

Write code prepared for future growth.

---

## Readability

Code is documentation.

Prefer readability over cleverness.

---

# HTML

Use semantic HTML whenever possible.

Avoid unnecessary wrappers.

Keep hierarchy clean.

Comment complex structures.

---

# CSS

CSS must follow the Design Tokens.

Never hardcode:

- colors
- spacing
- typography
- borders
- radius

Always use CSS Variables.

Organize styles by responsibility.

---

# JavaScript

Do not introduce JavaScript unless explicitly requested by the specification.

Prefer HTML and CSS solutions.

---

# Dependencies

Do not install dependencies.

Do not introduce frameworks.

Do not introduce libraries.

Unless explicitly requested.

---

# Project Structure

Respect the existing folder structure.

Do not reorganize files.

Do not rename directories.

Do not move files without authorization.

---

# Design Tokens

Every visual decision must originate from Design Tokens.

Never bypass them.

---

# Components

Components must:

- have one responsibility;
- be reusable;
- be independent;
- avoid project-specific logic.

---

# Patterns

Patterns compose Components.

Patterns never redefine Components.

---

# Templates

Templates compose:

- Layouts
- Patterns
- Components
- Diagram Types

Templates never introduce new Components.

---

# Diagram Framework

The Diagram Framework provides infrastructure.

It does not implement diagrams.

Roadmaps, UML, ERD, C4, Mind Maps and other diagram types will be implemented later.

---

# Documentation Comments

Complex files should contain descriptive comments.

Comments should explain:

- purpose
- responsibilities
- dependencies

Never explain obvious code.

---

# Validation

Before considering a task complete:

Verify that:

- implementation matches the specification;
- architecture was respected;
- scope was respected;
- acceptance criteria were satisfied;
- no unrelated files were modified.

---

# If Something Is Missing

If the specification is ambiguous:

Do not guess.

Stop.

Explain the ambiguity.

Request clarification.

---

# If Something Is Wrong

If implementation conflicts with the architecture:

Do not work around it.

Explain the conflict.

Wait for instructions.

---

# Definition of Done

A specification is complete only if:

- every requirement was implemented;
- every restriction was respected;
- acceptance criteria passed;
- architecture remained intact;
- documentation was respected;
- no unnecessary code was introduced.

---

# Response Format

After finishing every specification provide:

## Summary

Short description of the implementation.

---

## Files Modified

List every modified file.

---

## Acceptance Criteria

State whether every acceptance criterion was satisfied.

---

## Technical Notes

Relevant implementation decisions.

---

## Pending Items

Anything that could not be completed.

---

# Golden Rules

1. Documentation defines architecture.
2. Specifications define implementation.
3. Code never defines architecture.
4. Never implement beyond the requested SPEC.
5. Prefer reusable solutions.
6. Keep responsibilities separated.
7. Respect the project structure.
8. Validate before finishing.
9. Stop after completing the requested SPEC.
10. When in doubt, ask instead of assuming.

---

# Architecture Decision Rule

If during implementation you identify:

- repeated code,
- architectural smells,
- missing abstractions,
- opportunities for reuse,
- inconsistencies,

DO NOT implement the improvement immediately.

Instead:

1. Finish the requested SPEC.
2. Report the observation.
3. Explain the proposed improvement.
4. Wait for approval before changing the architecture.