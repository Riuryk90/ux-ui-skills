# Ethics

> Canonical operational knowledge. Derived from versioned research under `/research`. Do not edit projected runtime copies manually.

**Role**: consolidación operativa de `ER-001`–`ER-013` (matriz regulatoria/ética de UX). **Boundaries**: **`ETHICAL_RISK != LEGAL_CONCLUSION`** — señalar un riesgo ético/regulatorio no es asesoría legal definitiva. **`REGULATORY_GUIDANCE != BINDING_LAW`** — que una fuente sea oficial/regulatoria no implica que cada recomendación sea una obligación legal por sí misma. Ninguna entrada de este documento declara cumplimiento/incumplimiento legal confirmado. **Runtime**: `BOTH_RUNTIME`. **Size**: SMALL-MEDIUM.

Clasificación de 3 vías, nunca fusionadas: **`ETHICAL_CONCERN`** (riesgo señalable, sin fuente vinculante) · **`REGULATORY_GUIDANCE`** (orientación de autoridad, no obligación legal nueva) · **`BINDING_REQUIREMENT`** (disposición vinculante identificable, alcance acotado al artículo literal).

---

## Binding Requirements (`REGULATORY_REQUIREMENT`) — vinculante, jurisdicción acotada

| ER | Requisito | Disposición | Jurisdicción | Alcance vinculante | Related GP |
|---|---|---|---|---|---|
| ER-001 | Reversibilidad simétrica de decisiones de consentimiento | Art. 7(3) GDPR | UE/EEE | Solo retiro de consentimiento | GP-008 |
| ER-002 | Defaults no deben beneficiar a la plataforma sobre el usuario | Art. 25(2) GDPR | UE/EEE | Solo si involucra datos personales | GP-007 |
| ER-003 | Cancelar/borrar no debe requerir más pasos que contratar/crear | Art. 12(2) GDPR | UE/EEE | Solo borrado de cuenta/datos como ejercicio de derechos | GP-008 |
| ER-006 | Consentimiento no debe empaquetarse con términos generales | Art. 7(2) GDPR | UE/EEE | Empaquetado de consentimiento | — |
| ER-012 | Lenguaje claro y llano en información de datos/consecuencias | Art. 12(1) GDPR | UE/EEE | Solo comunicación sobre datos personales | — |
| ER-013 | Sin manipulación emocional al ejercer un derecho | Art. 12(2) + 5(1)(a) GDPR | UE/EEE | Solo ejercicio de derechos de protección de datos | GP-011 |

**Nota — "no crear ley global"**: ninguna de estas 6 reglas se trata como principio UX universal por sí sola. Donde alimentan un `GP`, el GP añade un criterio ético/UX independiente (reducción de fricción de salida, defaults centrados en el usuario, comunicación no coercitiva) que existe más allá del artículo específico — regla regulatoria y principio ético quedan como entidades separadas, nunca fusionadas.

## Regulatory Guidance — orientación de autoridad, no obligación legal nueva

| ER | Orientación | Fuente | Corroboración | Related GP |
|---|---|---|---|---|
| ER-004 | Indicadores de progreso/urgencia/escasez deben ser reales | FTC | Investigación académica independiente | GP-010 |
| ER-005 | Prueba social debe ser verificable y de origen identificable | FTC | Investigación académica independiente | GP-010 |
| ER-007 | Sin solicitudes repetidas bloqueantes tras rechazo explícito ("nagging") | EDPB (sin artículo trazable) | Investigación académica ("Nagging") | `NEEDS_LEGAL_VALIDATION` |
| ER-008 | Divulgación completa de costos antes del compromiso | FTC | Investigación académica independiente | GP-009 |
| ER-010 | Condiciones posteriores a "valor gratis" no deben ocultarse | FTC | Investigación académica independiente | GP-009 |

## Needs More Evidence — no usar con la misma confianza que lo anterior

| ER | Statement | Razón |
|---|---|---|
| ER-009 | Barras de progreso de onboarding deben reflejar avance real | Extrapolación por analogía — ninguna fuente primaria cataloga explícitamente "progreso fabricado" |
| ER-011 | Personalización temprana no debe inflar el costo de abandono (IKEA effect) | Conexión por analogía con ER-003, ninguna fuente estudia el IKEA effect como dark pattern directamente |

## Ethical Principles puros

Ninguno — ningún `ER` quedó clasificado como principio ético sin fuente regulatoria/de guidance tras la auditoría. Los criterios éticos generales derivados viven en `PRINCIPLES.md` (GP-007 a GP-011), cada uno con su fuente regulatoria citada explícitamente.

---

## Nota de alcance

- Ningún hallazgo constituye asesoría legal ni declaración de cumplimiento/incumplimiento formal — GDPR/FTC/DSA requieren asesoría legal calificada. Ver `BOUNDARIES.md` §Ethical/Regulatory Boundary.
- La jurisdicción importa: la mayoría de `ER` vinculantes son específicos de UE/EEE (GDPR); la evidencia FTC (EE. UU.) es `REGULATORY_GUIDANCE`, no ley directamente vinculante fuera de un proceso de aplicación real. Ningún `GP` presenta una regla de un solo país como universal sin esta distinción.

**Total: 13/13 ER.** Fuente: `research/synthesis/NORMATIVE-AND-REGULATORY-RULES.md` §Ethics/Regulatory.
