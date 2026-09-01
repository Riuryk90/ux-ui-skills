# Principles

> Canonical operational knowledge. Derived from versioned research under `/research`. Do not edit projected runtime copies manually.

**Role**: `GP` = Global Principle — criterio de diseño/revisión transversal, no implementación. Ninguno prescribe un componente, librería o valor visual específico. **Runtime**: `BOTH_RUNTIME` (build y review). **Size**: MEDIUM.

Ningún `GP` sustituye a un requisito normativo (`AR`) o regulatorio (`ER`) — donde existe uno, el `GP` cita el requisito (`Related normative`) y añade el criterio de diseño más amplio que ese requisito sostiene, sin relajarlo.

---

### GP-001 — Orientación y navegación estratificada para audiencias múltiples
La interfaz debe permitir responder siempre "¿dónde estoy? ¿qué puedo hacer? ¿a dónde puedo ir?". Cuando el producto sirve audiencias genuinamente distintas, el primer nivel de navegación debe mantenerse corto/escaneable, delegando audiencias secundarias a agrupaciones o a un índice exhaustivo.
- **Scope**: productos con 2+ audiencias genuinamente distintas y volumen de contenido suficiente.
- **Exceptions**: sitios de audiencia única/pequeña — la estratificación añade sobrecarga sin beneficio.
- **Trade-offs**: audiencias de menor tráfico quedan en capas secundarias (priorización real, no ausencia de servicio).
- **Confidence**: HIGH. **Related**: AR-012 (submenús operables por teclado) · Pattern PF-01 (Navigation).

### GP-002 — El foco de teclado nunca se elimina sin reemplazo
Todo componente enfocable por teclado debe tener indicador de foco visible con contraste suficiente. Remover el outline nativo sin sustituto igual o más visible es un defecto, no una decisión estética.
- **Scope**: todo componente interactivo, cualquier stack.
- **Exceptions**: el grosor ≥2px es nivel AAA (AR-003), no un mínimo AA universal — no exigirlo como si fuera AA. Foco agrupado con `:hover` es mitigación parcial, no fallo total.
- **Trade-offs**: ninguno legítimo — es la implementación de referencia.
- **Confidence**: HIGH. **Related**: AR-001, AR-002, AR-003, AR-004, AR-005 · AP-002 (foco global eliminado).

### GP-003 — El movimiento automático debe ser controlable
Contenido con movimiento/actualización automática que coexiste con otro contenido debe ofrecer pausa/detención/ocultamiento; animación disparada por interacción debe poder desactivarse, respetando la preferencia del sistema cuando esté disponible.
- **Scope**: hero sliders, marquees/tickers, contenido auto-actualizable, animación por interacción.
- **Exceptions**: movimiento esencial para la actividad o la información transmitida (excepción explícita del propio SC).
- **Trade-offs**: un carrusel con pausa genuina sigue siendo aceptable.
- **Confidence**: HIGH. **Related**: AR-009, AR-010, AR-011 · AP-001 (auto-rotación sin pausa) · Pattern PF-03 (Hero/Motion).

### GP-004 — Los campos de entrada requieren etiquetas persistentes asociadas programáticamente
Todo campo requiere un `<label>` (visible u oculto-accesible) asociado programáticamente. `placeholder` no es sustituto: desaparece al escribir y no todos los lectores de pantalla lo anuncian consistentemente.
- **Scope**: todo formulario, cualquier stack.
- **Exceptions**: label visualmente oculto (clip, no `display:none`) es válido cuando el propósito ya es comunicado por un ícono inequívoco.
- **Trade-offs**: ninguno legítimo frente a placeholder-only.
- **Confidence**: HIGH. **Related**: AR-013, AR-014, AR-015, AR-016, AR-017 · AP-003, AP-005 · Pattern PF-05 (Forms).

### GP-005 — Los mensajes de estado asíncronos deben anunciarse a tecnología de asistencia
Cuando una acción produce un resultado asíncrono (confirmación, error, validación), el mensaje debe ser determinable programáticamente (`aria-live`/`role="status"`/`role="alert"`), sin depender de que el foco esté cerca del mensaje.
- **Scope**: cualquier feedback in-page tras una acción.
- **Exceptions**: ninguna documentada.
- **Trade-offs**: ninguno legítimo.
- **Confidence**: HIGH. **Related**: AR-018 · AP-006 · Pattern PF-13 (Feedback/Status).

### GP-006 — Las afordancias interactivas deben ser genuinamente operables con el rol correcto
Un control debe implementarse con un elemento nativamente interactivo (o `role` + operabilidad de teclado equivalente) que exponga el rol/nombre/valor reales. Un elemento que *parece* interactivo sin serlo programáticamente es un defecto, no una simplificación válida.
- **Scope**: botones, campos, acordeones/disclosure, tarjetas clicables, cualquier control custom.
- **Exceptions**: ninguna — sin contraindicación legítima.
- **Trade-offs**: implementar sobre el elemento correcto puede costar más código — costo justificado.
- **Confidence**: HIGH. **Related**: AR-012, AR-013, AR-020 · AP-003, AP-004, AP-005 (espíritu).

### GP-007 — Los defaults deben servir el interés del usuario, no solo el del negocio
Cuando una interfaz preselecciona/resalta una opción, debe ser la más favorable para el usuario — especialmente con costo o datos personales — no la más rentable para la plataforma.
- **Scope**: cualquier preselección/resaltado (planes, checkboxes de consentimiento, add-ons).
- **Exceptions**: un default más restrictivo que frustra el propósito central del servicio, explicado transparentemente, no está cubierto.
- **Trade-offs**: ninguno legítimo cuando el default beneficia al negocio sin transparencia.
- **Confidence**: HIGH. **Related**: ER-002 (vinculante solo si involucra datos personales).

### GP-008 — El esfuerzo de salir no debe exceder el esfuerzo de entrar
Cancelar, borrar una cuenta o revertir una decisión no debe requerir más pasos que la acción original de contratar/crear/decidir.
- **Scope**: cancelación, borrado de cuenta, retiro de consentimiento, cualquier "deshacer".
- **Exceptions**: pasos de verificación de identidad proporcionalmente necesarios no cuentan como fricción indebida.
- **Trade-offs**: ninguno legítimo.
- **Confidence**: HIGH. **Related**: ER-001 (retiro de consentimiento, UE/EEE), ER-003 (borrado de datos, UE/EEE).

### GP-009 — Divulgación completa de costos antes del compromiso
Todos los costos (recurrentes, comisiones, condiciones de "gratis") deben mostrarse con prominencia comparable antes de completar la compra/registro, no después ni en letra pequeña desproporcionada.
- **Scope**: checkout, suscripciones, ofertas "gratis" condicionadas, financiamiento en cuotas.
- **Exceptions**: precio de referencia que enruta a negociación (ventas enterprise/B2B) es aceptable si no promete un checkout que el modelo de negocio no puede cumplir.
- **Trade-offs**: mostrar el costo total puede reducir conversión inmediata frente a anclar solo la cuota — aceptado a favor de la confianza del usuario.
- **Confidence**: HIGH. **Related**: ER-008, ER-010 · AP-011, AP-012 · Pattern PF-09 (Pricing).

### GP-010 — Los indicadores de progreso/urgencia/escasez/prueba social deben ser reales
Cualquier contador, cuenta regresiva, indicador de disponibilidad, testimonio o mensaje de actividad debe corresponder a un dato real — no a un valor fabricado para inducir una decisión más rápida.
- **Scope**: countdown timers, indicadores de stock, testimonios, contadores de actividad, barras de progreso.
- **Exceptions**: un contador real y auditable no está cubierto por esta restricción.
- **Trade-offs**: ninguno legítimo para el dato fabricado; el dato real sigue siendo técnica de conversión válida.
- **Confidence**: MEDIUM (el núcleo e-commerce es sólido; el sub-caso de progreso de onboarding fabricado — ER-009 — es evidencia débil, no eleva el conjunto a HIGH). **Related**: ER-004, ER-005, ER-009 · Pattern PF-10 (Social Proof).

### GP-011 — Sin lenguaje emocionalmente coercitivo contra el ejercicio de un derecho
La interfaz no debe usar culpa, FOMO o vergüenza específicamente cuando el usuario intenta cancelar, borrar una cuenta, retirar consentimiento o rechazar una oferta.
- **Scope**: flujos de cancelación, borrado, rechazo de ofertas, banners de consentimiento.
- **Exceptions**: comunicar una consecuencia real y neutral ("perderás acceso a X función") no está cubierto.
- **Trade-offs**: ninguno legítimo.
- **Confidence**: MEDIUM (componente normativo sólido; única evidencia de showcase es de una fuente con confidence LOW en origen). **Related**: ER-013 (vinculante UE/EEE para derechos GDPR) · AP-010.

### GP-012 — Evaluar el diseño en 3 niveles: visceral, conductual, reflexivo
Al revisar/diseñar, considerar explícitamente la impresión sensorial inmediata, la usabilidad funcional, y el significado/identidad reflejados — no solo la usabilidad funcional aislada.
- **Scope**: metodología de revisión/crítica — lente de evaluación, no checklist de construcción.
- **Exceptions**: no debe usarse para justificar decisiones puramente estéticas sin evidencia de usabilidad real.
- **Trade-offs**: ninguno — marco adicional de análisis, complementario a (no sustituto de) checklists de accesibilidad/usabilidad.
- **Confidence**: MEDIUM (fuente única de autoridad reconocida, sin convergencia de segunda clase de evidencia).

### GP-013 — Los datos informan el criterio de diseño, no lo sustituyen
Las decisiones deben apoyarse en datos cuando estén disponibles, pero el criterio (contexto, intención, principios) sigue siendo necesario para interpretarlos.
- **Scope**: cualquier decisión de diseño con datos de uso/negocio disponibles.
- **Exceptions**: en productos de escala masiva, validar con datos reales antes de rollout completo es más crítico — no es excepción al principio, es un contexto donde cambia el peso relativo dato/criterio.
- **Trade-offs**: ninguno — postura de equilibrio, no un extremo.
- **Confidence**: MEDIUM.

### GP-014 — Progressive disclosure: esencial primero, detalle bajo demanda — sin resolución universal frente a completitud
En general, mostrar lo esencial y revelar el detalle al interactuar reduce carga cognitiva; pero en dominios de alta densidad de datos (financieros, dashboards de power-user), mostrar todo por defecto con personalización opcional puede ser preferible. Depende del perfil de experiencia/frecuencia de la audiencia.
- **Scope**: navegación, formularios, onboarding, dashboards de audiencia casual/mixta.
- **Exceptions**: audiencia power-user recurrente y alfabetizada en dominios data-dense — ver CD-001 (`CONTEXTUAL-DECISIONS.md`).
- **Trade-offs**: ocultar información puede ser precisamente lo indeseado cuando el usuario necesita ver muchos datos a la vez.
- **Confidence**: HIGH para el mecanismo general; explícitamente NO universal — no elevar a regla incondicional. **Related**: Pattern PF-11 (Dashboard/Data-Dense) · CD-001.

### GP-015 — Tokens de diseño semánticos en vez de valores fijos
Colores, tipografía y otros valores reutilizados deben definirse como tokens semánticos centralizados, no como valores fijos repetidos por regla.
- **Scope**: proyectos CSS/SCSS de tamaño medio-grande, cualquier stack con sistema de temas.
- **Exceptions**: páginas triviales de una sola sección no necesitan la abstracción.
- **Trade-offs**: mayor esfuerzo inicial de definición del sistema de tokens — se amortiza con el mantenimiento.
- **Confidence**: HIGH. **Related**: facilita cumplir AR-002/AR-006 (contraste) de forma consistente. **No relacionado con** NH-08 (minimalismo) — ver `HEURISTICS.md`.

### GP-016 — Auditar consistencia por separado de corrección
Que un patrón esté implementado correctamente en un lugar no verifica que esté aplicado consistentemente en todas las instancias del mismo patrón — la consistencia intra-producto debe auditarse explícitamente, no asumirse.
- **Scope**: metodología de revisión/QA — aplica a cualquier auditoría de accesibilidad, patrones de interacción o design system.
- **Exceptions**: ninguna — la inconsistencia intra-producto es la norma observada, no la excepción.
- **Trade-offs**: auditar cada instancia en vez de una muestra cuesta más esfuerzo — justificado por la tasa de inconsistencia observada.
- **Confidence**: HIGH. **Related**: AP-004 · protocolo de verificación de NH-04.

### GP-017 — Auditar contenido/código heredado antes de publicar
Antes de entregar, verificar explícitamente la presencia de contenido/código heredado de otro producto/rebrand (clases no relacionadas, créditos ajenos, valores de formulario de otro rubro, navegación de demo sin cablear) — no asumir que fue limpiado por defecto.
- **Scope**: checklist de QA pre-entrega, cualquier producto derivado de template/boilerplate/rebrand.
- **Exceptions**: ninguna.
- **Trade-offs**: tiempo adicional de revisión pre-publicación — justificado por la tasa de recurrencia observada.
- **Confidence**: HIGH. **Related**: AP-007 (espíritu — riesgo de gobernanza/proceso).

---

## Índice de confianza

| Confidence | GP |
|---|---|
| HIGH | GP-001–009, GP-014–017 (13) |
| MEDIUM | GP-010, GP-011, GP-012, GP-013 (4) |
| LOW | ninguno |

**Total: 17/17 GP.** Fuente: `research/synthesis/CONSOLIDATED-PRINCIPLES.md`.
