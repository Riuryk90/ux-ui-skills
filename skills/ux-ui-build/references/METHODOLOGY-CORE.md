# Methodology Core

> Canonical operational knowledge. Derived from versioned research under `/research`. Do not edit projected runtime copies manually.

**Role**: fuente única del flujo de construcción y del flujo de revisión — evita que ambos diverjan si se mantuvieran por separado. **Runtime**: `BOTH_RUNTIME` — cada bundle carga el flujo que le corresponde como `ALWAYS_LOAD`, con referencia disponible al flujo de la otra postura. **Size**: SMALL.

---

## Build Workflow

**Estado: `METHODOLOGY_CANDIDATE`** — derivado del corpus, no una arquitectura de Skill impuesta; sujeto a revisión si evidencia futura sugiere otro orden (ej. accesibilidad chequeada en paralelo a cada paso, no solo al final).

```text
UNDERSTAND CONTEXT
↓
IDENTIFY USER GOAL
↓
IDENTIFY CONSTRAINTS
↓
STRUCTURE INFORMATION
↓
SELECT PATTERNS
↓
DESIGN INTERACTION
↓
CHECK ACCESSIBILITY
↓
CHECK ETHICAL RISKS
↓
CHECK RESPONSIVE / STATES
↓
REVIEW TRADE-OFFS
↓
OUTPUT
```

**Evidencia de soporte para este orden**: coincide con el patrón de análisis usado consistentemente en la investigación de origen de este proyecto (contexto/estructura primero, patrones/interacción en el medio, chequeos de accesibilidad/ética/responsive antes de la síntesis final). `CHECK ACCESSIBILITY` y `CHECK ETHICAL RISKS` se mantienen como pasos distintos, nunca fusionados (consistente con `ACCESSIBILITY.md`/`ETHICS.md` siempre separados). `REVIEW TRADE-OFFS` incluye auditar consistencia (GP-016) y contenido heredado (GP-017), no solo trade-offs de diseño nuevo.

**Integración de NH-02** (`INTEGRATED_INTO_CORE_METHODOLOGY`, sin archivo separado): el vocabulario/modelo mental del usuario real se verifica explícitamente en `UNDERSTAND CONTEXT` e `IDENTIFY USER GOAL` — antes de `STRUCTURE INFORMATION`, para no diseñar con jerga interna ni asumir un modelo mental equivocado del usuario.

## Review Workflow

**Estado: `CANONICAL_METHODOLOGY_SYNTHESIS`** — organiza actividades de evaluación ya establecidas (`HEURISTICS.md` §Boundaries, `BOUNDARIES.md`) en una secuencia operativa; no introduce ningún `NH`/`HR`/`GP`/`AP` nuevo.

```text
1. ESTABLISH SCOPE (qué se revisa, qué no)
2. IDENTIFY AUDIENCE / CONTEXT (mismo primer principio que build — NH-02)
3. RUN EXPERT_HEURISTIC_REVIEW (NH-01–10, ver HEURISTICS.md)
4. RUN ACCESSIBILITY_REVIEW (AR-001–020, ver ACCESSIBILITY.md)
5. RUN ANTI-PATTERN SCAN (AP-001–012, ver ANTI-PATTERNS.md)
6. CHECK ETHICAL / REGULATORY RISK (ER-001–013, ver ETHICS.md)
7. CROSS-REFERENCE POSITIVE CRITERIA (GP/BP como contraste, ver PRINCIPLES.md/BEST-PRACTICES.md)
8. ASSIGN SEVERITY + CONFIDENCE per finding (HR-002, ejes separados)
9. APPLY SINGLE_EVALUATOR_LIMITATION (HR-003) si es un único evaluador
10. OUTPUT — hallazgos con boundaries declarados (HR-012, HR-013: no equivale a user testing, no es veredicto de cumplimiento WCAG)
```

`MAY_MODIFY_CODE = FALSE` en esta postura — analiza y recomienda, no modifica directamente (frontera de postura, ver arquitectura de distribución).

## QUICK / DEEP (conceptual)

Dos modos de profundidad de aplicación del conocimiento — **sin sintaxis de invocación definida en este bloque** (decisión de implementación pendiente):

- **`QUICK`**: aplica el core `ALWAYS_LOAD` de cada postura (índices de GP/AP/Pattern Families, conciencia AR/ER, boundaries condensados) sin cargar el detalle `LOAD_ON_DEMAND` de cada archivo de referencia. **`QUICK != SHALLOW_REASONING`** — significa contexto mínimo necesario cargado, no menor rigor de juicio; los boundaries (`HR-001`–`003`, `SINGLE_EVALUATOR_LIMITATION`, límites de accesibilidad/ética) siguen aplicando íntegramente en modo `QUICK`.
- **`DEEP`**: carga selectivamente el detalle completo de los archivos de referencia que la tarea requiera. **`DEEP != LOAD_EVERYTHING`** — sigue siendo carga condicionada por relevancia de tarea (ver `PROGRESSIVE-DISCLOSURE-PLAN.md`), no un modo que ignore progressive disclosure.

---

Fuente: `research/synthesis/METHODOLOGY-BOUNDARIES.md` §Methodology flow candidate, `research/usability/HEURISTIC-EVALUATION-BOUNDARIES.md`, `research/architecture/PROGRESSIVE-DISCLOSURE-PLAN.md`.
