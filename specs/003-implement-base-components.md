# SPEC-003

# Implement Base Components

---

## Información General

| Campo | Valor |
|--------|--------|
| ID | SPEC-003 |
| Nombre | Implement Base Components |
| Estado | Ready |
| Prioridad | Alta |
| Versión | v0.1 |
| Dependencia | SPEC-002 |
| Documento de referencia | docs/03. Component Library.md |

---

# Contexto

El sistema de Design Tokens ya se encuentra implementado.

La siguiente etapa consiste en construir la primera versión de la Component Library del Documentation Design System.

Los componentes representan las unidades fundamentales de construcción del DDS.

Todo Layout, Pattern, Template y Diagram deberá construirse reutilizando exclusivamente estos componentes.

Este SPEC implementa únicamente componentes base.

No implementa lógica documental.

No implementa diagramas.

No implementa páginas.

---

# Objetivo

Implementar una biblioteca inicial de componentes HTML reutilizables que constituyan la base visual del Documentation Design System.

Todos los componentes deberán consumir exclusivamente Design Tokens.

---

# Alcance

Este SPEC implementa únicamente los Primitive Components definidos por el DDS.

Incluye:

- Estructura HTML
- Estilos CSS
- Organización
- Variantes básicas
- Documentación interna

No incluye:

- Patterns
- Templates
- Diagramas
- Layouts
- Páginas

---

# Archivos afectados

## HTML

```
src/components/

header.html

footer.html

card.html

badge.html

divider.html

legend.html
```

---

## CSS

```
src/assets/css/components.css
```

---

## Playground

```
playground/index.html
```

El Playground deberá mostrar todos los componentes implementados.

---

# Arquitectura

La Component Library deberá respetar la siguiente jerarquía.

```
Design Tokens

↓

Primitive Components

↓

Patterns

↓

Layouts

↓

Templates

↓

Pages
```

Los componentes nunca deberán depender de:

- Templates
- Diagramas
- Páginas

---

# Componentes

## Header

### Propósito

Representar el encabezado estándar del DDS.

### Responsabilidades

- Mostrar título
- Mostrar subtítulo
- Mostrar versión
- Mostrar metadata

### No responsabilidades

- Navegación
- Sidebar
- Breadcrumb

---

## Footer

### Propósito

Representar el pie estándar del documento.

### Responsabilidades

- Información del documento
- Número de página
- Versión
- Copyright

---

## Card

### Propósito

Contenedor reutilizable.

Será el componente más utilizado del DDS.

### Variantes

- Default
- Outlined
- Filled

---

## Badge

### Propósito

Mostrar estados.

### Variantes

- Primary
- Success
- Warning
- Danger
- Neutral

---

## Divider

### Propósito

Separar visualmente contenido.

### Variantes

- Horizontal
- Vertical

---

## Legend

### Propósito

Representar referencias visuales para diagramas.

Deberá permitir:

- símbolo
- color
- descripción

---

# Responsabilidades

Todos los componentes deberán:

- utilizar únicamente Semantic Tokens;
- reutilizar componentes cuando corresponda;
- mantener una única responsabilidad;
- ser independientes entre sí;
- ser reutilizables.

---

# Convenciones HTML

Todos los componentes deberán:

- utilizar HTML semántico;
- mantener indentación consistente;
- incluir comentarios descriptivos;
- evitar estructuras innecesarias.

Ejemplo:

```
<!--
Component

Purpose

Responsibilities

Variants
-->
```

---

# Convenciones CSS

Todos los estilos deberán ubicarse exclusivamente en:

```
components.css
```

No crear archivos CSS por componente.

La organización deberá realizarse mediante comentarios.

Ejemplo:

```
Header

--------------------------------

...

Card

--------------------------------

...

Badge

--------------------------------
```

---

# Design Tokens

Todos los componentes deberán utilizar exclusivamente:

```
var(--...)
```

Nunca utilizar:

- HEX
- RGB
- tamaños hardcodeados
- márgenes arbitrarios

---

# Variantes

Las variantes deberán implementarse utilizando clases modificadoras.

Ejemplo:

```
card

card--outlined

card--filled
```

Nunca duplicar componentes.

---

# Restricciones

No implementar:

- JavaScript
- Animaciones
- Responsive complejo
- Diagramas
- SVG
- Canvas
- Templates
- Patterns

---

# Accesibilidad

Todos los componentes deberán:

- utilizar etiquetas semánticas;
- respetar jerarquía HTML;
- mantener contraste adecuado;
- ser compatibles con navegación mediante teclado cuando corresponda.

---

# Calidad

Los componentes deberán sentirse como parte de una librería profesional.

Se espera un nivel de organización similar a:

- Carbon Design
- Material Design
- Fluent UI

Pero adaptado al contexto documental del DDS.

---

# Playground

Actualizar:

```
playground/index.html
```

El Playground deberá contener:

```
Header

↓

Cards

↓

Badges

↓

Dividers

↓

Legend

↓

Footer
```

Su objetivo es validar visualmente los componentes.

No deberá contener ejemplos del proyecto AI-SDOS.

---

# Criterios de aceptación

Se considerará completado cuando:

- Todos los componentes existen.
- Todos utilizan Design Tokens.
- Ningún componente contiene estilos inline.
- Todos poseen documentación interna.
- Todos poseen variantes básicas.
- Todos aparecen correctamente renderizados en el Playground.
- La Component Library puede reutilizarse inmediatamente.

---

# Definition of Done

- ✔ Componentes implementados.
- ✔ CSS organizado.
- ✔ HTML limpio.
- ✔ Variantes implementadas.
- ✔ Playground actualizado.
- ✔ Sin dependencias externas.
- ✔ Sin JavaScript.
- ✔ Compatible con el Base Layout.

---

# Fuera de alcance

Este SPEC no deberá:

- implementar Patterns;
- implementar Templates;
- implementar Diagramas;
- implementar Layouts;
- modificar Design Tokens;
- crear páginas del DDS;
- instalar dependencias.

---

# Resultado esperado

Al finalizar este SPEC, el Documentation Design System dispondrá de una biblioteca inicial de componentes reutilizables, completamente desacoplada de cualquier documento específico.

Estos componentes constituirán la base sobre la que se desarrollarán los Patterns (SPEC-004), el Diagram Engine (SPEC-005) y los Templates (SPEC-006), garantizando una arquitectura modular, consistente y mantenible.