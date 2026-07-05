# SPEC-005A — Organize Diagram Architecture

## Objetivo

Reestructurar la carpeta `src/diagrams` para establecer una arquitectura modular, escalable y reutilizable que sirva como base para todos los diagramas del Design Documentation System (DDS).

Esta SPEC no incorpora nuevos tipos de diagramas ni contenido específico del proyecto. Su único propósito es definir la organización interna del sistema gráfico.

---

# Dependencias

* SPEC-001 — Initialize DDS Project
* SPEC-002 — Implement Design Tokens
* SPEC-003 — Implement Base Components
* SPEC-004 — Implement Pattern Library
* SPEC-005 — Implement Diagram Framework

---

# Alcance

Reorganizar la estructura de `src/diagrams` de la siguiente manera:

```text
src/
└── diagrams/
    ├── primitives/
    │   ├── canvas.html
    │   ├── node.html
    │   ├── connector.html
    │   ├── group.html
    │   ├── boundary.html
    │   ├── swimlane.html
    │   ├── label.html
    │   ├── title.html
    │   ├── legend.html
    │   └── notes.html
    │
    ├── types/
    │   └── .gitkeep
    │
    ├── examples/
    │   └── .gitkeep
    │
    └── README.md
```

---

# Responsabilidad de cada carpeta

## primitives/

Contiene todos los elementos gráficos fundamentales del sistema.

Estos componentes representan la unidad mínima reutilizable para construir cualquier diagrama.

Ejemplos:

* Canvas
* Node
* Connector
* Group
* Boundary
* Swimlane
* Label
* Title
* Legend
* Notes

---

## types/

Reservada para las implementaciones de la Diagram Library.

Aquí se incorporarán posteriormente diagramas como:

* Context Diagram
* Container Diagram
* Component Diagram
* Deployment Diagram
* Sequence Diagram
* Flow Diagram
* Timeline
* Roadmap
* Decision Tree
* Mind Map
* Organization Chart

Su implementación corresponde a la SPEC-007.

---

## examples/

Reservada para ejemplos de uso del sistema de diagramas.

Los archivos contenidos en esta carpeta tendrán únicamente fines demostrativos y de validación visual.

No forman parte de la documentación oficial.

---

## README.md

Documentará:

* propósito de la carpeta
* arquitectura interna
* responsabilidades de cada subdirectorio
* reglas de reutilización
* flujo de composición de diagramas

---

# Reglas de arquitectura

La jerarquía deberá respetar el siguiente flujo de composición:

```text
Design Tokens
        ↓
Primitive Components
        ↓
Patterns
        ↓
Diagram Primitives
        ↓
Diagram Types
        ↓
Documentation Templates
        ↓
Project Documentation
```

Los diagramas nunca podrán omitir esta jerarquía.

---

# Restricciones

No implementar:

* tipos de diagramas
* diagramas de AI-SDOS
* ejemplos completos
* documentación del proyecto
* JavaScript
* frameworks externos

Esta SPEC únicamente reorganiza la arquitectura del sistema gráfico.

---

# Criterios de aceptación

La SPEC se considerará completada cuando:

* exista la estructura completa de carpetas definida
* todos los elementos del Diagram Framework residan en `primitives/`
* existan las carpetas `types/` y `examples/`
* exista un `README.md` documentando la arquitectura
* no se modifique el comportamiento de los componentes existentes
* la estructura permita incorporar nuevos tipos de diagramas sin reorganizaciones futuras

---

# Fuera de alcance

Esta SPEC no implementa:

* Diagram Library
* Documentation Pages
* Diagramas oficiales de AI-SDOS
* exportación
* generación automática
* contenido de documentación
