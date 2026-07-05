# SPEC-004

# Implement Patterns

---

# Información General

| Campo | Valor |
|--------|--------|
| ID | SPEC-004 |
| Nombre | Implement Patterns |
| Estado | Ready |
| Prioridad | Alta |
| Versión | v0.1 |
| Dependencia | SPEC-003 |
| Documento de referencia | docs/03. Component Library.md |

---

# Contexto

La Component Library ya proporciona los componentes fundamentales del Documentation Design System.

La siguiente etapa consiste en implementar la capa de Patterns.

Un Pattern representa una composición reutilizable de componentes que resuelve una necesidad frecuente de documentación sin pertenecer a un documento específico.

Los Patterns actúan como puente entre los Components y los Templates.

---

# Objetivo

Implementar la primera versión de la Pattern Library del DDS.

Los Patterns deberán construirse exclusivamente reutilizando componentes existentes.

No podrán redefinir estilos ni introducir nuevas reglas visuales.

---

# Alcance

Este SPEC implementa:

- Estructura de Patterns
- HTML reutilizable
- Estilos mínimos (si fueran necesarios)
- Organización del proyecto
- Playground

Este SPEC NO implementa:

- Templates
- Diagramas
- Layouts
- Páginas
- Componentes nuevos

---

# Archivos afectados

## HTML

```
src/patterns/

hero.html

metadata-panel.html

status-card.html

diagram-panel.html

section-header.html

dashboard-widget.html
```

---

## CSS

```
src/assets/css/components.css
```

Los Patterns deberán reutilizar los estilos existentes.

Solo podrán añadirse reglas específicas cuando resulte estrictamente necesario.

---

## Playground

```
playground/index.html
```

Actualizar para incluir todos los Patterns.

---

# Arquitectura

Los Patterns forman la siguiente capa del DDS.

```
Design Tokens

↓

Components

↓

Patterns

↓

Layouts

↓

Templates

↓

Pages
```

Los Patterns nunca deberán depender de:

- Templates
- Páginas
- Diagramas específicos

---

# Pattern Library

Implementar los siguientes Patterns.

---

## Hero

### Propósito

Introducir visualmente un documento.

### Composición

- Header
- Title
- Description
- Metadata

### Uso

Inicio de documentos.

---

## Metadata Panel

### Propósito

Mostrar información contextual.

### Composición

- Card
- Badge
- Divider

### Uso

Versiones.

Autores.

Estado.

Fechas.

---

## Status Card

### Propósito

Representar el estado de un elemento.

### Composición

- Card
- Badge
- Title

### Uso

Project State.

Roadmaps.

Dashboards.

---

## Diagram Panel

### Propósito

Contenedor estándar para diagramas.

### Composición

- Card
- Title
- Legend
- Notes

### Uso

Todos los diagramas.

---

## Section Header

### Propósito

Separar secciones importantes.

### Composición

- Title
- Divider

---

## Dashboard Widget

### Propósito

Representar información resumida.

### Composición

- Card
- Badge
- Metadata

---

# Responsabilidades

Todo Pattern deberá:

- reutilizar componentes existentes;
- mantener una única responsabilidad;
- no contener lógica documental;
- ser completamente reutilizable;
- ser independiente del contenido.

---

# Convenciones HTML

Cada Pattern deberá comenzar con un bloque descriptivo.

Ejemplo:

```
<!--

Pattern

Purpose

Composition

Dependencies

Variants

-->
```

---

# Dependencias

Los Patterns solo podrán utilizar:

- Components
- Design Tokens

Nunca podrán depender de:

- Templates
- Pages
- Diagram Engine

---

# Estilos

Los Patterns deberán:

- reutilizar componentes existentes;
- evitar duplicación;
- minimizar CSS adicional.

Todo nuevo estilo deberá documentarse.

---

# Variantes

Las variantes deberán implementarse mediante modificadores.

Ejemplo:

```
status-card

status-card--success

status-card--warning
```

Nunca crear múltiples versiones del mismo Pattern.

---

# Restricciones

No implementar:

- JavaScript
- Diagramas
- Layouts
- Templates
- Responsive avanzado
- SVG
- Canvas

---

# Calidad

Los Patterns deberán sentirse como composiciones oficiales del DDS.

No deberán percibirse como componentes aislados.

---

# Playground

Actualizar:

```
playground/index.html
```

Agregar una sección nueva.

```
Patterns

↓

Hero

↓

Metadata Panel

↓

Status Card

↓

Diagram Panel

↓

Section Header

↓

Dashboard Widget
```

Cada Pattern deberá mostrarse individualmente.

---

# Criterios de aceptación

Se considerará completado cuando:

- Todos los Patterns existen.
- Todos reutilizan Components.
- Ningún Pattern redefine el sistema visual.
- Todos utilizan Design Tokens.
- Todos aparecen correctamente renderizados en el Playground.
- La composición resulta consistente.

---

# Definition of Done

- ✔ Todos los Patterns implementados.
- ✔ HTML limpio.
- ✔ CSS mínimo.
- ✔ Sin duplicación.
- ✔ Playground actualizado.
- ✔ Documentación interna.
- ✔ Preparados para reutilización.

---

# Fuera de alcance

Este SPEC no deberá:

- implementar Templates;
- implementar Diagramas;
- implementar Layouts;
- modificar Components;
- modificar Tokens;
- crear páginas.

---

# Resultado esperado

Al finalizar este SPEC, el Documentation Design System dispondrá de una Pattern Library reutilizable que permitirá construir Templates complejos sin duplicar HTML ni estilos.

Los Patterns representarán las composiciones estándar del sistema y constituirán la base para la implementación del Layout Engine, Diagram Engine y Templates definidos en los siguientes SPEC.