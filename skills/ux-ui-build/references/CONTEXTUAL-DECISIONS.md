# Contextual Decisions

> Canonical operational knowledge. Derived from versioned research under `/research`. Do not edit projected runtime copies manually.

**Role**: tensiones donde el corpus muestra evidencia real de que no existe una única mejor respuesta — dependen del contexto (audiencia, densidad de información, madurez del producto, plataforma). Ninguna tensión aquí se inventó sin evidencia: cada `CD` cita convergencia o contraste real entre 2+ fuentes independientes. **Runtime**: `BOTH_RUNTIME`, `LOAD_ON_DEMAND` con puntero condicional en el core de ambas Skills. **Size**: TINY.

---

### CD-001 — Progressive disclosure vs. completitud/densidad de información
En dominios de alta densidad de datos, no existe resolución universal entre revelar información progresivamente (reduce carga cognitiva inicial) y mostrar todo por defecto (sirve mejor a un power-user recurrente).
- **Nivel epistémico**: `PARTIALLY_SUPPORTED` — 2 productos financieros reales resolviendo la misma tensión de formas opuestas, ambas defendibles. Evidencia de showcase, no investigación científica de uso real.
- **Variable determinante**: perfil de frecuencia/experiencia de la audiencia.
- **Related**: GP-014, NH-06, NH-07 · Pattern PF-11 (Dashboard/Data-Dense).
- **No forzar**: ninguna versión de la Skill debe presentar "progressive disclosure" ni "densidad por defecto" como la respuesta correcta universal para interfaces data-dense.

### CD-002 — Densidad de conversión/personalización vs. carga cognitiva
Ofrecer múltiples ejes de datos/contenido simultáneos mejora eficiencia de escaneo para quien ya sabe qué busca, pero incrementa carga cognitiva de decisión para quien no.
- **Nivel epistémico**: `PARTIALLY_SUPPORTED` — mismo par de fuentes que CD-001; faceta distinta de la misma tensión de fondo (densidad vs. carga cognitiva es el mecanismo; progressive disclosure vs. completitud es la manifestación de producto).
- **Variable determinante**: la misma que CD-001.
- **Related**: GP-014 · Pattern PF-11.

### CD-003 — Amplitud de audiencia/storytelling vs. velocidad de acceso al objetivo
Servir audiencias amplias con storytelling/navegación multi-capa da cobertura completa, pero añade pasos entre el usuario y su objetivo si ya sabe qué busca.
- **Nivel epistémico**: `PARTIALLY_SUPPORTED` — 3-4 sitios observados, sin datos de conversión/uso real que confirmen el costo cuantitativo de cada extremo.
- **Variable determinante**: si la audiencia típica ya conoce el nombre del producto/sección que busca (favorece navegación producto-primero) vs. necesita orientación por rol/necesidad primero (favorece estratificación por audiencia).
- **Related**: GP-001 · Pattern PF-01 (Navigation).

### CD-004 — Riqueza de variantes de venta (multi-demo) vs. riesgo de mantenimiento/consistencia
Ofrecer múltiples variantes/homes desde un solo producto amplía el atractivo de venta, pero cada variante es una oportunidad independiente de introducir/no corregir un defecto, a menos que exista separación real de datos/presentación.
- **Nivel epistémico**: `PARTIALLY_SUPPORTED` — patrón confirmado en código fuente real, sin datos de conversión que confirmen el beneficio de venta del extremo "más variantes". La cantidad de variantes no predice calidad por sí sola; la ausencia de separación de datos sí determina si una corrección se propaga.
- **Variable determinante**: si el stack permite separación real de datos/presentación — en ese caso el riesgo de inconsistencia baja sustancialmente; en HTML estático puro, cada variante es una superficie de riesgo independiente.
- **Related**: GP-016 (mitigación, no resolución) · Pattern PF-15 (Component Interaction/Architecture).

### CD-005 — Personalización vs. predictibilidad (evidencia débil, en observación)
Personalización temprana aumenta valor percibido para un usuario recurrente, pero un usuario nuevo puede preferir un estado predecible/por defecto sin configuración previa.
- **Nivel epistémico**: `WEAK_EVIDENCE` — se registra explícitamente como tensión a vigilar, no como hallazgo consolidado. La propia fuente de origen documenta "mala experiencia para un visitante nuevo" como su propio trade-off; no hay una segunda fuente independiente que confirme esta tensión específica. **No usar como si tuviera el mismo respaldo que CD-001–004.**
- **Related**: NH-07 (HR-008 exige citar esta debilidad de evidencia) · Pattern PF-11.

---

## Tensiones sugeridas pero NO registradas por falta de evidencia

Por disciplina explícita del corpus, estas tensiones **no** se elevan a `CD` porque no hay evidencia real y directa de ambos lados:
- **Motion vs. accessibility** — no es tensión sin resolución; la evidencia apunta consistentemente en una sola dirección (movimiento debe ser controlable) — vive como GP-003, no como CD.
- **Novelty vs. familiarity** — ninguna fuente del corpus la discute.
- **Brand expression vs. consistency** — los hallazgos relacionados son un defecto de higiene de contenido (GP-017), no una tensión legítima.
- **Abstraction vs. explicit control** — evidencia demasiado indirecta.
- **Automation vs. user control** — evidencia demasiado dispersa.

**Total: 5/5 CD.** Fuente: `research/synthesis/CONTEXTUAL-DECISIONS.md`.
