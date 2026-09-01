# Preferences & Guardrails

> Canonical operational knowledge. Derived from versioned research under `/research`. Do not edit projected runtime copies manually.

**Role**: registro explícito de elementos que **no** deben convertirse en reglas de la Skill — evita que gusto personal disfrazado de UX se filtre como principio validado. **`PREFERENCE != UX PRINCIPLE`**. **Runtime**: `BOTH_RUNTIME`, con regla de verificación en el core de ambas Skills (tanto build al proponer estilo, como review al evaluar estilo, deben consultar esto antes de afirmar una regla de estilo visual). **Size**: SMALL.

Dos ejes, nunca mezclados:
- **`OBSERVED_NON_RULE`** — elemento realmente detectado en el corpus, pero con alcance acotado para que no se generalice más allá de su fuente/contexto original. SÍ es un hallazgo de corpus, pero no-generalizable.
- **`PREVENTIVE_WATCHLIST`** — categoría que **ninguna fuente del corpus afirmó**. Se registra únicamente para impedir dogmatización futura. Nunca citar como "el corpus dice que X" — el corpus no dice nada al respecto, ni a favor ni en contra.

---

## A. Observado en el corpus — no generalizable (`OBSERVED_NON_RULE`)

| # | Elemento | Clasificación | Por qué no generalizar |
|---|---|---|---|
| 1 | Valores numéricos específicos de animación (curvas cubic-bezier, duraciones, umbrales de swipe) | `STYLE_CHOICE` | Elecciones de diseño de un autor específico para animación, no principios de UX/UI general |
| 2 | Supuesto de stack tecnológico (React/CSS/Framer Motion web; React Native+Reanimada mobile) | `STACK_CHOICE` | Una Skill agnóstica de framework no debe heredar estos supuestos salvo que el proyecto destino ya use ese stack |
| 3 | Lista curada de librerías de un autor específico | `STACK_CHOICE` | El *mecanismo* (lista opinionada + tabla antipatrón→corrección) es adoptable; la lista concreta es específica de producto/autor |
| 4 | Decisiones de lenguaje muy específicas de Apple/iOS (Swift, concurrencia, Testing) | `PLATFORM_SPECIFIC` | Irrelevante fuera de un contexto nativo-Apple |
| 5 | Traducción literal de mecanismos de plataforma Apple como estándar universal (Tab Bar, SF Symbols, nombres de color) | `PLATFORM_SPECIFIC` | El *principio* subyacente (orientación clara, tokens semánticos) sí se generaliza — GP-001/GP-015 — el mecanismo literal no traduce directo a web/otras plataformas |
| 6 | Tono de marca / voz personal del autor en documentación técnica | `STYLE_CHOICE` | Posicionamiento editorial de un producto/curso específico, no requisito de arquitectura ni de contenido UX |
| 7 | Preferencia estética Apple-style / minimalismo de sistema como estándar visual universal | `PLATFORM_SPECIFIC` / `WEAK_EVIDENCE` | No confundir "Apple resuelve bien la orientación/tokens/progressive disclosure" (evidencia real, ya en GP-001/014/015) con "el lenguaje visual de Apple es el estándar UX universal" (no evidenciado) |

## B. Categorías de vigilancia — NO detectadas en el corpus (`PREVENTIVE_WATCHLIST`)

Ninguna entrada de esta sección es un hallazgo de corpus.

| Categoría | Clasificación | Estado |
|---|---|---|
| Esquinas redondeadas siempre | `PREFERENCE` | No afirmado por ninguna fuente |
| Minimalismo siempre | `PREFERENCE` | No afirmado — no confundir con GP-014/NH-08 (progressive disclosure/relevancia, no minimalismo visual) |
| Glassmorphism | `STYLE_CHOICE` | No afirmado por ninguna fuente |
| Preferencia de gradientes | `STYLE_CHOICE` | No afirmado por ninguna fuente |
| Duraciones de animación específicas fuera de la instancia A.1 | `STYLE_CHOICE` | Solo existe la instancia ya documentada en A — no confundir ambas |
| Preferencia de color general | `PREFERENCE` | No afirmado — el corpus solo cubre contraste normativo (AR-002/AR-006), no teoría/preferencia de color |

---

## Nota de aplicación

Ningún elemento de este documento debe citarse en la Skill como regla, ni siquiera como "preferencia recomendada por defecto". Si una recomendación empieza a sugerir alguno de estos elementos como regla general, debe señalarse explícitamente que su origen es gusto/plataforma/stack específico, no evidencia consolidada (GP/BP/AR/ER).

**Total: 7/7 Observed Non-Rules, 6/6 Preventive Watchlist (13 entradas).** Fuente: `research/synthesis/PREFERENCES-AND-NON-RULES.md`.
