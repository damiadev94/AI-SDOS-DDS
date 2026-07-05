# AI-SDOS Documentation Design System

A reusable system for building technical, architectural, and engineering documentation using only HTML, CSS, and SVG.

---

## Objective

The DDS provides a unified visual and structural architecture for all documentation produced within the AI-SDOS ecosystem. Its goal is to make documentation as maintainable, scalable, and reusable as the software it describes.

---

## Philosophy

| Principle | Description |
|-----------|-------------|
| Documentation as Code | All documentation is versioned, maintained, and evolved as source files |
| Specs First | Specifications precede implementation |
| Component First | Documents are built by composing reusable components |
| HTML First | HTML is the primary format for construction |
| SVG First | Graphical elements use SVG for quality and scalability |
| Print First | Every page is designed for correct PDF export from the start |
| Tool Agnostic | No dependency on specific design or publishing tools |
| Consistency over Creativity | Visual uniformity takes priority over individual preference |
| Accessibility by Default | Contrast, hierarchy, and semantic markup are non-negotiable |

---

## Architecture

```
tokens.css          Single source of truth for all visual values
    │
    ▼
reset.css           Predictable baseline — no opinion
    │
    ▼
typography.css      Font family, scale, weight, line-height
layout.css          Grid, flex, spacing structure
components.css      Visual styles for UI components
diagrams.css        Diagram canvas, node, connector infrastructure
utilities.css       Single-purpose utility classes
print.css           Print and PDF export rules
```

Design Token hierarchy:

```
Primitive Tokens    Raw values — never used directly by components
    │
    ▼
Semantic Tokens     Meaning-assigned values — used by all components
    │
    ▼
Component Tokens    Component-specific configurations
```

---

## Project Structure

```
dds/
├── README.md
├── src/
│   ├── assets/
│   │   ├── css/
│   │   │   ├── reset.css
│   │   │   ├── tokens.css
│   │   │   ├── typography.css
│   │   │   ├── layout.css
│   │   │   ├── components.css
│   │   │   ├── diagrams.css
│   │   │   ├── utilities.css
│   │   │   └── print.css
│   │   ├── fonts/
│   │   └── icons/
│   ├── components/
│   │   ├── header.html
│   │   ├── footer.html
│   │   ├── card.html
│   │   ├── badge.html
│   │   ├── divider.html
│   │   └── legend.html
│   ├── layouts/
│   │   └── base.html
│   ├── templates/
│   │   ├── documentation.html
│   │   ├── dashboard.html
│   │   ├── diagram.html
│   │   └── reference.html
│   ├── pages/           (empty — populated per project)
│   └── diagrams/        (empty — populated per diagram spec)
├── playground/
│   └── index.html
└── exports/             (empty — build output target)
```

---

## How to Run

No build tools. No dependencies. No package manager.

Open any HTML file directly in a browser:

```
dds/playground/index.html     Visual component reference
dds/src/layouts/base.html     Shell structure
dds/src/templates/*.html      Page templates
```

For PDF export: open the target page in a browser and use the browser's native print-to-PDF function. All `print.css` rules are pre-configured for A4 output.

---

## CSS Import Order

The stylesheet stack must be imported in this exact order:

```html
<link rel="stylesheet" href="assets/css/reset.css">
<link rel="stylesheet" href="assets/css/tokens.css">
<link rel="stylesheet" href="assets/css/typography.css">
<link rel="stylesheet" href="assets/css/layout.css">
<link rel="stylesheet" href="assets/css/components.css">
<link rel="stylesheet" href="assets/css/diagrams.css">       <!-- diagram pages only -->
<link rel="stylesheet" href="assets/css/utilities.css">
<link rel="stylesheet" href="assets/css/print.css" media="print">
```

---

## Design Token Rules

All components must:

- Use only Semantic Tokens (never Primitive Tokens directly)
- Never hardcode color values
- Never use arbitrary sizes outside the defined scale
- Never define their own typography
- Never modify Primitive Tokens

---

## Roadmap

```
[✓] 01. Foundation          Philosophy, principles, goals, scope
[✓] 02. Design Tokens       Color, typography, spacing, radius, elevation, motion
[ ] 03. UI Components       Card, Node, Badge, Connector, Arrow, Legend, etc.
[ ] 04. Diagram Library     Roadmap, C4, ERD, Flow, UML, Mind Map, etc.
[ ] 05. Templates           Documentation, Dashboard, Diagram, Reference
[ ] 06. Export System       PDF, HTML export pipeline
[ ] 07. Examples            Reference implementations for each diagram type
[ ] 08. Implementation      First production diagrams for AI-SDOS
```

---

## Current State

| Area | Status |
|------|--------|
| Foundation | Defined |
| Design Tokens | Defined |
| CSS Infrastructure | Complete |
| Component Shell | Complete |
| Templates | Scaffolded |
| UI Components | Pending |
| Diagram Library | Pending |
| Export System | Pending |
| Examples | Pending |

---

## Constraints

- HTML and CSS only
- No JavaScript
- No frameworks (no Bootstrap, no Tailwind, no React)
- No preprocessors (no Sass, no Less)
- No npm, no node, no build pipeline
- No external dependencies
