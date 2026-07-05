# src/diagrams

Diagram system for the AI-SDOS Documentation Design System (DDS).

---

## Architecture

```
src/diagrams/
├── primitives/   — Fundamental graphic elements (reusable building blocks)
├── types/        — Diagram type implementations (reserved — see SPEC-007)
├── examples/     — Visual validation examples (non-authoritative)
└── README.md     — This file
```

---

## Composition hierarchy

Every diagram in the DDS must respect this composition order. No layer may
skip a level.

```
Design Tokens
      ↓
Primitive Components  (src/assets/css/components.css)
      ↓
Patterns              (src/assets/css/diagrams.css)
      ↓
Diagram Primitives    (src/diagrams/primitives/)
      ↓
Diagram Types         (src/diagrams/types/)
      ↓
Documentation Templates  (src/templates/)
      ↓
Project Documentation    (src/pages/)
```

---

## primitives/

Contains the minimum reusable graphic elements from which any diagram is
composed. Each file is a self-contained HTML partial — no DOCTYPE, no CSS
imports. They are composed into full pages by Diagram Types or Templates.

| File | Class | Purpose |
|---|---|---|
| `canvas.html` | `dds-diagram`, `dds-diagram__canvas`, `dds-diagram__svg` | Diagram drawing area and SVG overlay |
| `node.html` | `dds-node`, `dds-node--{variant}` | Single visual unit within a diagram |
| `connector.html` | `dds-connector`, `dds-connector--{variant}` | SVG line or path between two nodes |
| `group.html` | `dds-group`, `dds-group__label`, `dds-group__content` | Labeled region grouping related nodes |
| `boundary.html` | `dds-group` (boundary role) | Visible perimeter defining a system scope |
| `swimlane.html` | `dds-group` (lane role) | Horizontal or vertical partitioned lane |
| `label.html` | `dds-diagram-label` | Short text associated with a graphic element |
| `title.html` | `text-h4` | Diagram title |
| `legend.html` | `dds-legend`, `dds-legend__item`, `dds-legend__swatch` | Symbology key for node variants |
| `notes.html` | `text-small text-secondary` | Clarifying annotations below a diagram |

### Reuse rules

- Primitives never define domain meaning (Entity, Actor, Service, etc.).
  Domain meaning belongs to Diagram Types.
- Primitives never import CSS or declare styles. They rely exclusively on
  Design Tokens surfaced through the existing CSS stack.
- Primitives never contain JavaScript.

---

## types/

Reserved for Diagram Type implementations (SPEC-007).

Each diagram type is a complete standalone HTML page that composes
Diagram Primitives into a specific diagram pattern (e.g. Context Diagram,
Sequence Diagram, Roadmap).

Implementations reside in `src/diagram-library/` as of SPEC-007.

---

## examples/

Reserved for demonstrative examples used for visual validation.

Files here are non-authoritative — they exist only to verify that the
system renders correctly. They are not part of official project documentation.

---

## Conventions

- CSS imports use the stack: `reset → tokens → typography → layout →
  components → diagrams → utilities → print`
- No JavaScript in any diagram file
- No hardcoded colors or sizes — use Design Tokens only
- SVG path `d` attributes and positional attributes (`x`, `y`) must use
  fixed pixel values. `calc()` is invalid inside SVG attributes.
- Node variants: `--primary`, `--success`, `--warning`, `--error`
- Connector variants: `--primary`, `--dashed`
