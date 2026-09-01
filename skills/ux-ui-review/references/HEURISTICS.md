# Heuristics

> Canonical operational knowledge. Derived from versioned research under `/research`. Do not edit projected runtime copies manually.

**Role**: marco de evaluación heurística de usabilidad — 10 heurísticas de Nielsen (`NH-01`–`10`) + 14 reglas operativas candidatas (`HR-001`–`014`) + modelo de severidad. **Boundaries**: `EXPERT_HEURISTIC_REVIEW != USER_TESTING` — una heurística no es requisito WCAG, norma técnica, ley, criterio de certificación ni garantía de usabilidad; es un principio general de evaluación experta que puede incluso entrar en conflicto con otra. `ISSUE_SEVERITY != EVIDENCE_CONFIDENCE`. **Runtime**: `REVIEW_RUNTIME` únicamente. **Size**: MEDIUM (101 líneas — el documento más denso del corpus junto a `PRINCIPLES.md`, justificado por ser el aparato de evaluación heurística completo: 10 marcos + 14 reglas de aplicación + modelo de severidad + boundaries, consumido únicamente por la postura de revisión).

---

## Las 10 heurísticas (`NH-01`–`10`)

Formato compacto: definición · límite contextual crítico · falso positivo típico · related.

### NH-01 — Visibility of System Status
El sistema debe mantener al usuario informado de su estado mediante feedback apropiado y oportuno. **Límite**: operaciones locales instantáneas no necesitan spinner — exigir feedback visible para todo sería sobre-aplicar. **Falso positivo típico**: señalar ausencia de indicador de carga en una operación imperceptible. **Related**: GP-005, GP-003 · AR-018 · AP-006, AP-009 · PF-13.

### NH-02 — Match Between System and the Real World
La interfaz debe usar el vocabulario y modelo mental del usuario real, no jerga interna. **Límite**: una audiencia genuinamente experta (ej. dashboards financieros) tiene su propio "lenguaje real", que sí incluye términos técnicos — jerga sin explicar puede ser una decisión deliberada correcta, no un defecto. **Falso positivo típico**: señalar terminología técnica apropiada para una audiencia experta como "jerga". **Related**: ER-012 (espíritu, alcance distinto — GDPR). Sin GP dedicado — dimensión propia (`ADDS_NEW_DIMENSION`).

### NH-03 — User Control and Freedom
El usuario debe poder salir de un estado/acción no deseada de forma rápida y predecible ("emergency exit"). **Límite**: no exige "deshacer" literal para toda acción — algunas son inherentemente finales; el punto es una vía de salida clara, no reversión mágica universal. **Falso positivo típico**: señalar ausencia de "deshacer" cuando ya existe una vía de vuelta equivalente de bajo costo. **Related**: GP-008, GP-006, GP-011 · BP-001, BP-004 · AR-016 · ER-001, ER-003, ER-013 · PF-02, PF-07.

### NH-04 — Consistency and Standards
El mismo término/ícono/acción debe significar lo mismo en todo el producto; seguir convenciones de plataforma/industria. 4 niveles: interna, de plataforma, de dominio, de design-system. **Límite**: no exige que pantallas con propósitos distintos se vean idénticas — la consistencia es de significado/patrón, no de uniformidad visual literal. **Falso positivo típico**: señalar variedad visual legítima entre tipos de página distintos como inconsistencia. **Related**: GP-015, GP-016 · BP-005 · AR-020 · PF-15.

### NH-05 — Error Prevention
Mejor prevenir el error que solo explicarlo bien después. Distingue *slips* (acción no intencionada, se previene con restricciones/affordance) de *mistakes* (modelo mental equivocado, se previene con mejor correspondencia — ver NH-02). **Límite crítico**: no asumir que "mostrar confirmación siempre" es buena práctica — sobre-confirmar acciones de bajo riesgo genera fatiga de confirmación y reduce la efectividad real. Trade-off fricción-vs-prevención siempre a declarar. **Falso positivo típico**: señalar ausencia de confirmación en una acción de bajo riesgo y fácilmente reversible. **Related**: GP-008, GP-006 · BP-001 · AP-003 · AR-016 · PF-05.

### NH-06 — Recognition Rather than Recall
Minimizar la carga de memoria haciendo elementos/acciones/opciones visibles, en vez de exigir recordarlos. **Límite**: no significa "mostrar todo todo el tiempo" — tensiona directamente con progressive disclosure; resolución vía CD-001 (`CONTEXTUAL-DECISIONS.md`), no un extremo u otro. **Falso positivo típico**: señalar una opción diferida deliberadamente (progressive disclosure legítimo) como "carga de memoria". **Related**: GP-001, GP-004, GP-014 (tensión explícita, no resuelta silenciosamente) · BP-003 · AP-005 · AR-013 · PF-05, PF-01, PF-07; tensión directa con PF-11.

### NH-07 — Flexibility and Efficiency of Use
Servir bien tanto al usuario novato como al experto, sin que optimizar para uno perjudique al otro (atajos ocultos para novatos, visibles/útiles para expertos). **Límite crítico**: no asumir que la personalización siempre mejora la UX — conectar con CD-005 (`WEAK_EVIDENCE`, no tratar como más sólida de lo que es). **Falso positivo típico**: señalar una interfaz simple sin personalización como deficiente cuando su audiencia es enteramente novata o de uso único. **Related**: GP-014 · PF-11; tensión CD-005.

### NH-08 — Aesthetic and Minimalist Design
Las interfaces no deben contener información irrelevante o rara vez necesaria. **Tratamiento especial — NO es "minimalismo visual obligatorio"**: es sobre relevancia/señal-ruido, no sobre estilo visual (minimalismo, whitespace, monocromía, estética "Apple"). Un diseño denso/maximalista puede satisfacer esta heurística perfectamente si cada elemento es relevante para la tarea real. **Cruce obligatorio** con `PREFERENCES-GUARDRAILS.md` — nunca citar NH-08 para justificar "minimalismo siempre" como regla. **Falso positivo típico**: señalar un dashboard denso como "violación estética" cuando cada elemento es genuinamente relevante para su audiencia experta. **Related**: GP-014 (**no** GP-015 — tokens son sobre consistencia, no minimalismo, relación explícitamente excluida) · PF-11.

### NH-09 — Help Users Recognize, Diagnose, and Recover from Errors
Los mensajes de error deben estar en lenguaje llano, indicar precisamente el problema y sugerir constructivamente una solución. **Límite crítico**: no todo error necesita explicar su causa exacta — en contextos con implicación de seguridad (ej. login fallido), un mensaje deliberadamente vago es la práctica correcta, no una violación. Nunca recomendar revelar detalle diagnóstico con implicación de seguridad (fuera de alcance AppSec, ver `BOUNDARIES.md`). **Falso positivo típico**: señalar un mensaje de autenticación deliberadamente ambiguo como "violación de claridad". **Related**: GP-004, GP-005 · AP-006 · AR-014, AR-015 · PF-05, PF-13.

### NH-10 — Help and Documentation
Lo mejor es no necesitar explicación adicional; cuando hace falta, debe ser fácil de encontrar, buscar y aplicar. **Límite**: la existencia de buena documentación no excusa una interfaz confusa que podría simplificarse — usar documentación extensa como sustituto de arreglar la interfaz es en sí mismo un hallazgo de riesgo, no una mitigación válida. **Falso positivo a evitar**: tratar "tenemos buena documentación" como defensa suficiente ante un flujo fundamentalmente confuso. **Related**: GP-001.

### Nielsen vs WCAG / Ethical UX / Business Conversion

- **`NH-xxx` = `USABILITY_HEURISTIC`; `AR-xxx` (WCAG) = `ACCESSIBILITY_STANDARD`.** Pueden cruzarse, uno no sustituye al otro — un hallazgo que toca ambos se cita con ambas referencias por separado, nunca fusionado en un veredicto de cumplimiento.
- **`USABILITY != ETHICAL UX`.** Una interfaz puede satisfacer las 10 heurísticas y aun así ser manipulativa (ej. confirmshaming claro, consistente y con feedback inmediato — cumple NH-01/NH-04 mientras explota un sesgo). Ambas capas se mantienen independientes.
- **Resultados de negocio (conversión) son una dimensión distinta**, fuera del alcance de una evaluación heurística en sí — no justificar ni descartar un hallazgo heurístico citando impacto en conversión sin evidencia directa.

---

## Severity Model

Escala 0–4 (Nielsen, verbatim/paráfrasis):
**0** — no es un problema de usabilidad · **1** — cosmético, no imperativo arreglar · **2** — menor, prioridad baja · **3** — mayor, prioridad alta · **4** — catástrofe, imperativo arreglar antes de publicar.

Factores: **frequency** (¿común o rara?) · **impact** (¿fácil o difícil de superar?) · **persistence** (¿de una vez o recurrente?) · **market impact** (afecta popularidad pese a ser "objetivamente" fácil de resolver).

**`ISSUE_SEVERITY` vs `EVIDENCE_CONFIDENCE`** — ejes independientes, siempre reportados por separado (misma disciplina que `ANTI-PATTERNS.md`): severidad = qué tan grave *si es real*; confianza = qué tan seguro es que el hallazgo es real y no un falso positivo.

## Single Evaluator Limitation

Fuente verificada directamente: "severity ratings from a single evaluator are too unreliable to be trusted" — recomendada la media de 3 evaluadores independientes; "each individual... is likely to miss some of the potential usability issues", de ahí 3–5 evaluadores recomendados. **Aplicación directa**: si la Skill opera como evaluador único, todo hallazgo de severidad/completitud debe marcarse explícitamente `SINGLE_EVALUATOR_LIMITATION` — nunca presentado con la confianza de un panel de 3–5.

---

## Reglas operativas (`HR-001`–`014`)

| HR | Regla | Confidence | Related |
|---|---|---|---|
| HR-001 | Un hallazgo de "heurística violada" nunca se reporta sin contexto de usuario/tarea/severidad/confianza | HIGH | GP-012 |
| HR-002 | Severidad y confianza se evalúan y reportan como ejes separados, nunca combinados en una etiqueta | HIGH | — |
| HR-003 | Una revisión heurística de un solo evaluador debe marcarse `SINGLE_EVALUATOR_LIMITATION` — estructural, sin excepciones | HIGH | — |
| HR-004 | Hallazgos de NH-08 deben justificarse por relevancia/señal-ruido, nunca por ausencia de minimalismo/whitespace/estética Apple | HIGH | GP-014 |
| HR-005 | Hallazgos de NH-04 deben especificar cuál de los 4 niveles de consistencia aplica — nunca exigir uniformidad visual entre pantallas de propósito distinto | HIGH | GP-015, GP-016, BP-005 |
| HR-006 | Recomendar confirmación (NH-05) exige declarar explícitamente el trade-off fricción-vs-prevención; no recomendar confirmación por defecto en acciones de bajo riesgo | MEDIUM | GP-008, BP-001 |
| HR-007 | Hallazgos de NH-06 que recomienden mostrar más información deben verificarse contra CD-001, nunca recomendar "mostrar todo" sin considerar audiencia | HIGH | GP-014 |
| HR-008 | Recomendaciones de personalización (NH-07) deben citar el costo de predictibilidad — cruce con CD-005, evidencia débil | MEDIUM | GP-014 |
| HR-009 | Hallazgos de "jerga" (NH-02) deben justificarse contra la audiencia real documentada, no asumida | MEDIUM | — |
| HR-010 | Hallazgos de NH-09 nunca deben recomendar revelar detalle diagnóstico con implicación de seguridad | MEDIUM-HIGH | GP-004 |
| HR-011 | "Documentación extensa" nunca es defensa suficiente ante un hallazgo de NH-10 — puede ser en sí mismo el hallazgo | HIGH | GP-001 |
| HR-012 | Una revisión heurística de la Skill nunca se presenta como equivalente a testing con usuarios reales — declaración explícita requerida en la salida | HIGH | — |
| HR-013 | Un hallazgo heurístico nunca se etiqueta como veredicto de cumplimiento WCAG — ambos marcos se citan por separado | HIGH | GP-002–006 |
| HR-014 | Un conflicto entre heurísticas (ej. NH-06 vs NH-08) debe declararse explícitamente, nunca resolverse en silencio | HIGH | GP-014 |

**Total: 14/14 HR.** Confidence: HIGH=10, MEDIUM=3, MEDIUM-HIGH=1 (contado como MEDIUM en el tri-nivel).

---

## Boundaries — actividades de evaluación (7 tipos, no fusionar)

| Actividad | ¿La Skill la ejecuta directamente? |
|---|---|
| `EXPERT_HEURISTIC_REVIEW` (marco NH-01–10) | Sí, sujeta a `SINGLE_EVALUATOR_LIMITATION` |
| `ACCESSIBILITY_REVIEW` (AR-001–020 como criterio) | Sí — nivel distinto de `EXPERT_HEURISTIC_REVIEW`, nunca fusionar veredictos |
| `FORMAL_ACCESSIBILITY_AUDIT` (herramientas + revisión humana calificada, declaración A/AA/AAA) | No |
| `USER_TESTING` (participantes humanos reales) | No |
| `ANALYTICS_VALIDATION` (confirmación con datos de uso/negocio reales) | No |
| `LEGAL_COMPLIANCE_REVIEW` | No |
| `SECURITY_REVIEW` | No — prioridad sobre recomendación de usabilidad cuando ambas chocan (ver NH-09) |

**Total: 10/10 NH.** Fuente: `research/usability/NIELSEN-HEURISTICS-ANALYSIS.md`, `HEURISTIC-CANDIDATE-RULES.md`, `HEURISTIC-EVALUATION-BOUNDARIES.md`.
