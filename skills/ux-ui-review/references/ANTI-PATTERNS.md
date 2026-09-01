# Anti-Patterns

> Canonical operational knowledge. Derived from versioned research under `/research`. Do not edit projected runtime copies manually.

**Role**: `AP` = mecanismo de riesgo confirmado en el corpus — no una declaración de incumplimiento normativo/legal. Cada entrada se relaciona con `AR`/`ER`/`GP` como candidato a auditar, nunca como veredicto. **`severity`** (qué tan grave si es real) y **`confidence`** (qué tan seguro es que el hallazgo es real) se mantienen **explícitamente separados** — nunca un único "HIGH/MEDIUM/LOW" ambiguo. AppSec/seguridad de backend queda fuera de este catálogo (`OUT_OF_SCOPE_FOR_UXUI_SKILL`). **Runtime**: `REVIEW_RUNTIME` únicamente. **Size**: MEDIUM.

---

| AP | Anti-patrón | Severity | Confidence | Context | Exceptions / contraejemplo | Related |
|---|---|---|---|---|---|---|
| AP-001 | Contenido rotativo automático (hero/carrusel/marquee) sin control de pausa visible y operable, >5s, coexiste con otro contenido | HIGH | HIGH | Hero sliders, marquees/tickers en posiciones de alta visibilidad | Control "Reproducir/Pausa" observado es contraejemplo positivo | GP-003, AR-011 |
| AP-002 | Reset CSS que remueve `outline`/`box-shadow` de foco globalmente sin regla `:focus`/`:focus-visible` de reemplazo | HIGH | HIGH | Afecta toda la superficie interactiva del sitio | Foco=hover es mitigación parcial, no fallo total | GP-002, AR-001, AR-002, AR-005 |
| AP-003 | Campo de texto simulado con `window.prompt()` en vez de `<input>` HTML real | HIGH | MEDIUM (fuente única, pero instancia sistémica sin ambigüedad) | Checkout, login, búsqueda | Contraejemplo directo en el mismo lote de productos: uso de `<input>` real | GP-006, AR-013, AR-020 |
| AP-004 | Trigger de expandir/colapsar sobre elemento no interactivo (`<div>`/`<h4>`), sin `role="button"`, `tabIndex` ni `onKeyDown` | HIGH | HIGH | Secciones de FAQ/disclosure | Contraejemplo directo, mismos vendors, en otra página del mismo producto | GP-006, GP-016, AR-012, AR-020 |
| AP-005 | Formulario dependiente solo de `placeholder`, sin `<label>` persistente asociado | HIGH | HIGH | Formularios de contacto/newsletter | Un contraejemplo positivo confirmado en el corpus (5/5 campos correctos) | GP-004, AR-013 |
| AP-006 | Mensaje de éxito/error tras envío mostrado como cambio visual/CSS sin `aria-live`/`role="status"` | MEDIUM | HIGH | Formularios con feedback de envío asíncrono | Un contraejemplo positivo (`role="alert" aria-live="assertive"`) | GP-005, AR-018 |
| AP-007 | Widget/overlay de accesibilidad de terceros presentado como solución primaria, sin evidencia de estructura semántica subyacente resuelta | MEDIUM | MEDIUM | Sitios que usan un overlay comercial como medida visible | Un overlay como complemento de una base semántica ya sólida no es este riesgo | GP-017 (espíritu) |
| AP-008 | Contenido primario concentrado casi en su totalidad detrás de tabs/carrusel, sin vista lineal alternativa | MEDIUM | LOW (fuente única) | Páginas de producto B2B que comprimen mucho contenido en una URL | El patrón tabs/carrusel en sí es legítimo — el riesgo es la concentración total sin alternativa | GP-006, AR-012, AR-020 |
| AP-009 | Arquitectura 100% client-side sin contenido de respaldo (HTML inicial es solo shell) | MEDIUM | MEDIUM (síntoma confirmado; conclusión de riesgo real es inferencia) | SPAs de alto valor comercial que priorizan interactividad rica | SSR/hidratación cuidadosa puede no tener ninguno de estos problemas | — |
| AP-010 | Copy de rechazo de consentimiento con tono asimétrico/informal frente al de aceptación | MEDIUM | LOW (fuente única) | Banners de consentimiento con copy de marca personalizado | Si "aceptar" tuviera tono igualmente informal, la asimetría no existiría | GP-011, ER-013 |
| AP-011 | Framing de "gratis" sin precondición de compra/suscripción igualmente prominente | LOW | LOW | Productos con capas de "gratis" condicionado (freemium, add-ons) | Un contraejemplo positivo explícito: gratis sin ninguna precondición oculta | GP-009, ER-008, ER-010 |
| AP-012 | Precio mensual como cifra visualmente dominante, costo total relegado a disclaimers en letra pequeña | LOW | LOW | Financiamiento de productos de alto valor | El framing de cuota mensual es legítimo — el anti-patrón es la desproporción de prominencia, no el financiamiento en sí | GP-009, ER-008 |

## Resumen

| Severity | AP | Confidence | AP |
|---|---|---|---|
| HIGH | AP-001–005 (5) | HIGH | AP-001, AP-002, AP-004, AP-005, AP-006 (5) |
| MEDIUM | AP-006–010 (5) | MEDIUM | AP-003, AP-007, AP-009 (3) |
| LOW | AP-011, AP-012 (2) | LOW | AP-008, AP-010, AP-011, AP-012 (4) |

Severity y confidence no correlacionan linealmente (ej. AP-003 es severity HIGH / confidence MEDIUM). **Total: 12/12 AP.** Fuente: `research/synthesis/ANTI-PATTERN-TAXONOMY.md`.
