# Best Practices

> Canonical operational knowledge. Derived from versioned research under `/research`. Do not edit projected runtime copies manually.

**Role**: `BP` = recomendación concreta y beneficiosa, respaldada por evidencia real pero de una o dos fuentes — no alcanza el umbral de convergencia de un `GP`. **`BEST_PRACTICE != REQUIREMENT`**: ninguna `BP` es obligatoria por sí misma; cada una es un caso de aplicación concreto, típicamente de un `GP` más amplio. **Runtime**: `BUILD_RUNTIME` únicamente (review puede citar una BP por nombre sin necesitar el catálogo completo). **Size**: SMALL.

---

| BP | Recomendación | Scope | Exceptions | Confidence | Related GP / normative |
|---|---|---|---|---|---|
| BP-001 | Confirmación neutral de dos pasos antes de una acción destructiva/irreversible (lenguaje sin culpabilizar, consecuencia clara) | Cualquier acción destructiva/irreversible | Ninguna | LOW (fuente única) | GP-008, GP-011 |
| BP-002 | Desglose completo de costos visible antes del botón de confirmación final (no solo subtotal) | Checkout con costos variables | Ninguna | LOW | GP-009, ER-008 |
| BP-003 | Label visualmente oculto (clip, no `display:none`) cuando el propósito ya es comunicado por un ícono inequívoco | Campos cuyo propósito ya es visual (ej. búsqueda) | No usar como excusa general para ocultar labels que sí aportan claridad | LOW | GP-004, AR-013 |
| BP-004 | Cierre de overlays/modales/paneles de búsqueda full-screen también por tecla `Escape`, no solo botón visual | Overlays, modales, paneles full-screen | Ninguna | LOW | GP-006, AR-012 |
| BP-005 | Breakpoints declarados como mapa nombrado (`small`/`medium`/`large`), no valores numéricos sueltos repetidos por `@media` | Proyectos SCSS/Sass con 3+ breakpoints | Proyectos muy pequeños de un solo breakpoint no lo necesitan | MEDIUM (2 fuentes) | GP-015 |
| BP-006 | Etiquetado visible del contenido publicitario/patrocinado mezclado con contenido editorial ("PUBLICIDAD" o equivalente) | Sitios de contenido con monetización mezclada con editorial/datos | Ninguna | LOW | GP-009, GP-010 |
| BP-007 | Advertencia proactiva de fraude/suplantación en secciones donde una marca reconocible es blanco plausible (ej. Careers) | Marcas grandes y reconocibles con riesgo de suplantación | Ninguna — bajo costo, sin downside identificado | LOW | GP-010 |
| BP-008 | Reductores de fricción explícitos y verdaderos ("no requiere tarjeta", "cancela cuando quieras") justo antes de un CTA con fricción percibida real | CTA de conversión con fricción real (pago, suscripción, compromiso de tiempo) | Los reductores deben ser verdaderos — uno falso cae bajo GP-010 | LOW | GP-009, GP-010, ER-008 |
| BP-009 | Nombre accesible textual (`aria-label`/`title`) en controles cuyo único indicador visual es color/ícono (ej. swatches de color) | Selectores de color/variante visual en e-commerce/filtros | Ninguna | LOW | GP-004, GP-006, AR-013, AR-020 |

**Total: 9/9 BP.** Todas `LOW` o `MEDIUM` — ninguna `HIGH` por diseño: una BP con convergencia de 2+ clases de evidencia fuertes se habría promovido a `GP`. Fuente: `research/synthesis/BEST-PRACTICES.md`.
