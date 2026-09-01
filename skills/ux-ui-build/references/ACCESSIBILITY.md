# Accessibility

> Canonical operational knowledge. Derived from versioned research under `/research`. Do not edit projected runtime copies manually.

**Role**: consolidación operativa de `AR-001`–`AR-020` (WCAG 2.2). **Boundary**: `ACCESSIBILITY_REVIEW != FORMAL_WCAG_AUDIT` — aplicar estos criterios durante diseño/revisión es núcleo de la Skill; declarar cumplimiento/incumplimiento formal (A/AA/AAA) requiere auditoría con herramientas y revisión humana calificada, que la Skill no realiza. **`SOURCE AUTHORITY != BINDING LEGAL FORCE`**: ningún hallazgo de este documento es una declaración de compliance formal. **Runtime**: `BOTH_RUNTIME`. **Size**: MEDIUM.

**Distinción de nivel de conformidad**: AA es el nivel de referencia típico de la industria; **AAA es un nivel superior, no un mínimo universal** — nunca presentar un requisito AAA como si fuera AA sin decirlo explícitamente (AR-003, AR-008, AR-009 son AAA).

---

## Requisitos normativos (`NORMATIVE_REQUIREMENT`, texto directo del estándar)

| AR | Requisito | SC | Nivel | Related GP |
|---|---|---|---|---|
| AR-001 | Indicador de foco visible en al menos un modo de operación | 2.4.7 Focus Visible | AA | GP-002 |
| AR-002 | Contraste ≥3:1 del indicador de foco vs. fondo | 1.4.11 Non-text Contrast | AA | GP-002 |
| AR-003 | Perímetro ≥2px + contraste ≥3:1 foco/no-foco | 2.4.13 Focus Appearance | **AAA** | GP-002 |
| AR-004 | Foco no completamente oculto por contenido del autor | 2.4.11 Focus Not Obscured (Min) | AA | GP-002 |
| AR-006 | Contraste texto/fondo ≥4.5:1 (normal) / ≥3:1 (grande) | 1.4.3 Contrast (Minimum) | AA | — |
| AR-007 | Objetivos táctiles ≥24×24 CSS px | 2.5.8 Target Size (Minimum) | AA | — |
| AR-008 | Objetivos táctiles ≥44×44 CSS px (controles importantes) | 2.5.5 Target Size (Enhanced) | **AAA** | — |
| AR-009 | Animación disparada por interacción debe poder desactivarse | 2.3.3 Animation from Interactions | **AAA** | GP-003 |
| AR-011 | Movimiento/actualización automática >5s debe poder pausarse | 2.2.2 Pause, Stop, Hide | A | GP-003 |
| AR-012 | Toda funcionalidad operable por teclado | 2.1.1 Keyboard | A | GP-006 |
| AR-013 | Etiquetas/instrucciones para entrada de usuario | 3.3.2 Labels or Instructions | A | GP-004 |
| AR-014 | Identificación de error de entrada en texto | 3.3.1 Error Identification | A | GP-004 |
| AR-015 | Sugerencias de corrección de error, cuando se conocen | 3.3.3 Error Suggestion | AA | GP-004 |
| AR-016 | Reversibilidad/confirmación en compromisos legales/financieros/de datos | 3.3.4 Error Prevention (Legal, Financial, Data) | AA | GP-004 |
| AR-017 | Autenticación sin prueba de función cognitiva obligatoria | 3.3.8 Accessible Authentication (Min) | AA | GP-004 |
| AR-018 | Mensajes de estado determinables programáticamente | 4.1.3 Status Messages | AA | GP-005 |
| AR-019 | Alternativa sin arrastre para funcionalidad de drag | 2.5.7 Dragging Movements | AA | — |
| AR-020 | Nombre/rol/valor determinables programáticamente | 4.1.2 Name, Role, Value | A | GP-006 |

## Guía / técnicas oficiales (`OFFICIAL_GUIDANCE` / `IMPLEMENTATION_TECHNIQUE`)

Interpretan o documentan un requisito — no son el texto normativo en sí.

| AR | Tipo | Contenido | Related SC / GP |
|---|---|---|---|
| AR-005 | Failure documentada | Remover `outline:none` sin reemplazo falla 1.4.11+2.4.7+2.4.13 simultáneamente | AR-002/001/003, GP-002 |
| AR-010 | Técnica reconocida | `prefers-reduced-motion: reduce` es técnica suficiente (C39/SCR40), no el SC en sí | 2.3.3, GP-003 |

---

## Críticos para revisión (resumen operativo)

- **Foco**: visible (AR-001), contraste ≥3:1 (AR-002), no oculto (AR-004); nunca remover sin reemplazo (GP-002).
- **Teclado**: toda funcionalidad operable (AR-012); ningún control custom sin equivalente de teclado.
- **Etiquetas**: persistentes y asociadas programáticamente (AR-013); `placeholder` no es sustituto.
- **Contraste**: texto 4.5:1 normal / 3:1 grande (AR-006); foco 3:1 (AR-002).
- **Movimiento**: pausable si automático y >5s (AR-011); desactivable si es por interacción (AR-009, AAA).
- **Mensajes de estado**: determinables programáticamente, `aria-live`/`role="status"`/`role="alert"` (AR-018).
- **Formularios/errores**: identificación (AR-014), sugerencia de corrección cuando se conoce (AR-015), reversibilidad en compromisos legales/financieros/de datos (AR-016).
- **Nombre/rol/valor**: expuestos programáticamente para cualquier control custom (AR-020).
- **Objetivos táctiles**: 24×24 mínimo (AA); 44×44 es refuerzo AAA, no mínimo universal.
- **Drag**: alternativa sin arrastre disponible (AR-019).
- **Autenticación**: sin prueba de función cognitiva obligatoria (AR-017).

## Nota de alcance normativo

- Ningún hallazgo de este documento constituye declaración de cumplimiento/incumplimiento formal — WCAG requiere auditoría con herramientas y revisión humana; ver `BOUNDARIES.md` §Accessibility Boundary.
- La jurisdicción/nivel de conformidad importa: no presentar un requisito AAA como si fuera AA sin decirlo.
- Ver `HEURISTICS.md` §Nielsen vs WCAG — un hallazgo heurístico y uno normativo se citan siempre por separado, nunca fusionados en un solo veredicto.

**Total: 20/20 AR.** Fuente: `research/synthesis/NORMATIVE-AND-REGULATORY-RULES.md` §Accessibility.
