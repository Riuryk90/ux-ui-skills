# Boundaries

> Canonical operational knowledge. Derived from versioned research under `/research`. Do not edit projected runtime copies manually.

**Role**: qué queda explícitamente fuera del núcleo de la Skill, y las fronteras de accesibilidad/ética que deben mantenerse aunque el conocimiento relacionado sí sea parte del núcleo. **`AGENT_OBSERVATION != USER_EVIDENCE`**. **Runtime**: `BOTH_RUNTIME` — versión condensada siempre cargada en ambas Skills, versión completa bajo demanda. **Size**: SMALL.

---

## Out of Scope (núcleo de la Skill)

Detectar una señal adyacente está permitido; actuar como si fuera autoridad definitiva en esa materia, no:

- **AppSec / seguridad de backend** — CSRF, sanitización server-side, autenticación/autorización, inyección, hardening.
- **Asesoría legal** — ningún GP/AP/entrada de `ETHICS.md` constituye asesoría legal definitiva.
- **Certificación WCAG completa** — ver §Accessibility Boundary.
- **Penetration testing** — sin relación con UX/UI.
- **SEO auditing completo** — señales de UX que afectan SEO pueden observarse; auditoría técnica completa (metadata, sitemap, indexación) no es núcleo.
- **Brand strategy completa** — la Skill trabaja con decisiones de UI que expresan marca (GP-015), no define estrategia de marca.
- **Marketing strategy completa** — puede señalar riesgo ético de conversión (GP-007–011), no diseña estrategia de adquisición.
- **Backend architecture / database design / deployment / infra** — fuera de alcance.
- **Analytics implementation** — "los datos deben informar el diseño" (GP-013) es criterio, no implementación de tracking.

Si una señal adyacente aparece (ej. backend inseguro observado al analizar un formulario), se registra como `ADJACENT_TECHNICAL_FINDING`, `Scope: OUT_OF_SCOPE_FOR_UXUI_SKILL`, sin promoverse a catálogo normativo.

---

## Accessibility Boundary

- **`CORE_DESIGN_RESPONSIBILITY`**: aplicar principios WCAG básicos en diseño/revisión es núcleo — 6/17 GP están fundamentados directamente en AR.
- **`FORMAL_ACCESSIBILITY_AUDIT`**: fuera del núcleo. Ninguna entrada de `ACCESSIBILITY.md` declara cumplimiento/incumplimiento normativo confirmado — nunca declarar compliance formal sin auditoría con herramientas y revisión humana calificada.

## Ethical / Regulatory Boundary

- **`CORE_ETHICAL_CONSIDERATION`**: señalar riesgo ético/manipulativo es núcleo (GP-007–011, todos con requisito normativo citado y acotado).
- **`LEGAL_COMPLIANCE_REVIEW`**: fuera del núcleo salvo módulo futuro explícito. **`SOURCE AUTHORITY != BINDING LEGAL FORCE`**. Lo que la Skill puede señalar: `ETHICAL_RISK`, `REGULATORY_RISK` (candidato a auditar). Lo que no puede hacer: emitir asesoría legal definitiva ("esto viola el GDPR") sin abogado calificado.

## Design/Build vs. Expert Review vs. Formal Usability Testing

Tres actividades distintas, ejecutores distintos:

1. **DESIGN/BUILD** — aplicar GP/BP/AR/ER/patrones al construir o modificar. Ejecutable directamente.
2. **EXPERT REVIEW** (heurística) — auditar contra un marco de criterios reconocido sin usuarios reales. Ejecutable directamente por la Skill/agente.
3. **FORMAL USABILITY TESTING** — observar usuarios reales interactuando con el producto para validar hallazgos empíricamente. **No ejecutable directamente** — requiere reclutamiento, sesiones en vivo/asíncronas, análisis de comportamiento humano real. La Skill puede señalar **cuándo** se necesita, no **realizarlo**.

Una revisión heurística por agente NO equivale a una prueba con usuarios reales — miden cosas distintas y tienen niveles de evidencia distintos.

## Accessibility Review vs. Testing (4 niveles, no fusionar)

1. **Skill accessibility review** — aplicar AR/GP-002–006 como criterio en diseño/revisión de código o markup. Núcleo, ejecutable directamente.
2. **Formal WCAG conformance audit** — herramientas especializadas + revisión humana calificada, declaración A/AA/AAA. Fuera del núcleo.
3. **Usability testing con foco en accesibilidad** — participantes reales, típicamente dependientes de tecnología de asistencia. Fuera del núcleo.
4. **Assistive technology testing completo** — verificación manual con lectores de pantalla reales (NVDA, JAWS, VoiceOver), switches, magnificadores. Distinto de (2) — requiere operar la tecnología directamente. Fuera del núcleo.

Que la Skill haga bien (1) no implica (2), (3) ni (4).

## Actividades de evaluación heurística (ver detalle completo en `HEURISTICS.md`)

`EXPERT_HEURISTIC_REVIEW` y `ACCESSIBILITY_REVIEW` — ejecutables directamente. `FORMAL_ACCESSIBILITY_AUDIT`, `USER_TESTING`, `ANALYTICS_VALIDATION`, `LEGAL_COMPLIANCE_REVIEW`, `SECURITY_REVIEW` — no ejecutables directamente por la Skill.

---

Fuente: `research/synthesis/METHODOLOGY-BOUNDARIES.md`, `research/usability/HEURISTIC-EVALUATION-BOUNDARIES.md`.
