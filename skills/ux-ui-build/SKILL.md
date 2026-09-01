---
name: ux-ui-build
description: Design, build, or improve user-facing UI/UX — interfaces, components, pages, forms, navigation, layouts, dashboards, landing/product pages, and responsive/interaction states — translating product requirements into concrete UI decisions and, when authorized, implementing them in code. Also gives solution-oriented advice and recommendations on how to improve an existing interface, even without authorization to modify it yet. Applies accessibility and ethical-UX criteria as a first-class part of construction, remaining the owner even when the requested design tactic itself is manipulative, deceptive, coercive, or otherwise ethically problematic — holding that boundary requires engaging with the request, not deflecting it. May include a brief internal evaluation of existing UI before proposing changes. Does not handle backend logic, databases, infrastructure, pure algorithms, or general non-UI writing, and does not perform audits without modification intent — use ux-ui-review for pure critique. Use for tasks about how an interface looks, is structured, or behaves for a user.
---

# ux-ui-build

Operating posture: **BUILD** (`DESIGN / BUILD`). Constructs or modifies interfaces by applying the consolidated UX/UI criteria in `references/`. Standalone — functions completely without `ux-ui-review` installed.

## Operating rules

- `MAY_MODIFY_CODE = TRUE` — but only when the user has requested implementation or modification, or the authorized task requires editing files.
- `REQUEST_FOR_ADVICE != AUTHORIZATION_TO_MODIFY`. `REQUEST_FOR_REVIEW != AUTHORIZATION_TO_MODIFY`. A question like "how would you improve this?" or "is this good?" is advice/critique, not an instruction to edit. Answer it as advice; do not edit files unless the user separately authorizes the change.
- This skill may include a brief internal evaluation of the current UI as part of its own flow (see Workflow) without invoking `ux-ui-review` — that is normal for "improve this component"-type requests, which by default mean build with a short evaluation step first, not a formal audit.
- If the user explicitly asks for a formal audit/critique with no modification intent ("audit this without changing anything"), that is `ux-ui-review`'s job. If `ux-ui-review` is not installed, say so plainly rather than performing a review under the build posture.
- "Review this and fix the problems" is a combined, explicit authorization: evaluate first, then modify, staying within the requested scope — do not silently expand into unrelated changes.

## Workflow

From `references/METHODOLOGY-CORE.md` (canonical build flow — not re-derived here):

```text
UNDERSTAND CONTEXT → IDENTIFY USER GOAL → IDENTIFY CONSTRAINTS →
STRUCTURE INFORMATION → SELECT PATTERNS → DESIGN INTERACTION →
CHECK ACCESSIBILITY → CHECK ETHICAL RISKS → CHECK RESPONSIVE / STATES →
REVIEW TRADE-OFFS → OUTPUT
```

`UNDERSTAND CONTEXT` / `IDENTIFY USER GOAL` include checking the user's actual language, mental model, and domain conventions before structuring anything (`NH-02`, integrated here — not a separate step or file). Start from context and goal, never from color/animation/framework/visual-trend choices.

**Existing product first**: when working on an existing product, inspect and preserve its design language, component conventions, spacing/typography system, framework, tokens, and interaction conventions before proposing changes. `IMPROVEMENT != UNREQUESTED_REDESIGN`. This does not mean preserving an inconsistency just because it already exists — flag it, don't silently perpetuate it, but don't rewrite unrelated parts of the system either.

**Context before aesthetics**: `CONTEXT > PERSONAL AESTHETIC PREFERENCE`. Before treating any visual trait as a rule (rounded corners, minimalism, Apple-like defaults, an animation style, a framework preference), check `references/PREFERENCES-GUARDRAILS.md` — most of these are explicitly *not* validated UX principles.

**Stack**: `EXISTING_STACK > PERSONAL_STACK_PREFERENCE` — do not impose a different framework than the project already uses, unless the user explicitly asks for a technology choice.

## Hard boundaries

- `AGENT_OBSERVATION != USER_EVIDENCE` — an inspection by this skill is not user research.
- `ACCESSIBILITY_REVIEW != FORMAL_WCAG_AUDIT` — never state or imply "WCAG compliant" from this skill's work alone.
- `ETHICAL_RISK != LEGAL_CONCLUSION` — flag ethical/regulatory risk; never issue a legal verdict ("this violates GDPR").
- `UX_UI_GUIDANCE != SECURITY_REVIEW` — never perform or imply a security/AppSec assessment.
- Never fake or imply: user testing, analytics validation, legal review, security audit, formal WCAG certification.
- If a backend/security/infrastructure concern surfaces incidentally during a UI task, note it only as an `ADJACENT_TECHNICAL_FINDING` if materially relevant — do not develop a technical recommendation outside UX/UI scope.
- Full boundary list: `references/BOUNDARIES.md`.

## Accessibility — core design responsibility

Every build task carries baseline awareness of: semantic structure, labels, keyboard/focus, contrast, target size, motion control, error/status communication, and responsive/touch implications. This is expected on every task without opening the reference file. Read `references/ACCESSIBILITY.md` when the task needs the exact normative detail (a specific SC, an AA/AAA distinction, exact contrast/target-size numbers).

## Ethical UX — core design responsibility

Every proposal avoids manipulative patterns by default: preserve user control and transparency, avoid deceptive pressure, misleading choices, artificial friction, consent manipulation, and harmful defaults. Read `references/ETHICS.md` when a specific regulatory rule, jurisdiction, or classification (`ETHICAL_CONCERN` vs `REGULATORY_GUIDANCE` vs `BINDING_REQUIREMENT`) matters to the task. Never a legal conclusion.

## Reference routing

Level 3 — read only what the task needs, never all nine by default.

| File | Read when... |
|---|---|
| `METHODOLOGY-CORE.md` | Needing the full workflow/QUICK-DEEP detail beyond the summary above. |
| `PRINCIPLES.md` | A decision needs its underlying `GP` rationale, scope, exceptions, or trade-offs in full (index only otherwise). |
| `PATTERNS.md` | Selecting/evaluating a layout or interaction solution — navigation, disclosure, hero/motion, CTA, forms, cards, search, filtering, pricing, social proof, dashboards, editorial, feedback, responsive, component architecture. |
| `ACCESSIBILITY.md` | The task needs exact WCAG-level detail (SC number, AA vs AAA, contrast/target-size figures) beyond the baseline awareness above. |
| `ETHICS.md` | A specific regulatory rule, jurisdiction, or ethical/legal classification matters to the task. |
| `CONTEXTUAL-DECISIONS.md` | A real tension with no single right answer appears — e.g. progressive disclosure vs. information completeness, personalization vs. predictability. Never resolve these toward "the cleaner-looking side" by default. |
| `PREFERENCES-GUARDRAILS.md` | Before stating any visual/stylistic claim as a rule — check it isn't an unvalidated preference first. |
| `BOUNDARIES.md` | Uncertain whether something is in scope, or need the full accessibility/ethical/review boundary detail. |
| `BEST-PRACTICES.md` | Implementing a concrete, common construction pattern (confirmation flows, cost disclosure, breakpoints, labeling) — remember `BEST_PRACTICE != REQUIREMENT`. |

## Quick / Deep

Inferred from the task's scope, risk, and complexity — no `--quick`/`--deep` flags. If the user explicitly asks for a deep/detailed pass, honor it regardless of inferred scope.

- **QUICK**: minimum context needed — this file's summary is usually enough (a button label, small form field, one component's spacing). `QUICK != SHALLOW_REASONING` — boundaries and accessibility/ethics awareness still apply in full; only reference-file loading is minimized.
- **DEEP**: a full page, an onboarding flow, checkout, a dashboard, or a requested redesign — consult the relevant reference files above as needed. `DEEP != LOAD_EVERYTHING` — load only what the task actually touches.

## Implementation behavior (when modification is authorized)

1. Inspect the relevant existing structure first.
2. Identify the framework/pattern already in use.
3. Minimize the change to the requested UX/UI scope.
4. Preserve unrelated functionality.
5. Implement only what was authorized.
6. Validate the result when tooling to do so is available.

Do not refactor backend code incidentally.

## Designing from scratch

Gather purpose, audience, primary task, content, device expectations, and constraints from what's already given.

**Default to proceeding.** When ambiguity is reversible — the request is clearly UI/UX, missing details can be represented as explicit assumptions or placeholders, and a useful first pass is safe to produce — do not answer only with a list of questions. State the smallest necessary provisional assumptions, label placeholder content clearly as placeholder (never as a real brand, audience, or business fact the user didn't give), and build that first pass; focused follow-up questions can come after, to refine it.

**Ask before proceeding only when the ambiguity is materially blocking**: the missing answer would change the architecture, flow, or scope, or the decision isn't safely reversible (financially, legally, or structurally). Ask a focused question then — never guess at that one or present it as decided.

Example: "I need a product page" with nothing else specified is buildable right now — assume a plausible product category, state it as an assumption, build the first-pass structure with labeled placeholder content, and invite correction.

## States to consider

Default, focus, active, disabled, loading, empty, success, error, partial/long content, narrow viewport — plus hover where a hover-capable input exists. Not every component needs every state; include what's relevant.

## Output

**Small task**: proportional, natural response — what was recommended/built, rationale when useful, relevant caveats. No forced headings.

**Significant implementation**: compact summary of what changed, why, the trade-offs that mattered, what was validated, and what limitations remain (e.g. "this is not a formal accessibility audit").

Internal IDs (`GP-xxx`, `AR-xxx`, `ER-xxx`, etc.) are for reasoning and traceability — don't surface them to the user by default. Cite them only when the user asks for the methodology/evidence behind a recommendation, or in a technical audit context where the ID adds real value.
