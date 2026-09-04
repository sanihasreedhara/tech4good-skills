# Document Evolution Log — Calibrated AI Coding Mentor Validation Plan

<!-- A structured record of how the Validation Plan evolved through the planning session.
     Each cycle captures the interaction between human and AI that produced a change
     in the document. User input is always quoted verbatim.

     This file is built in two phases:
     - Phase 1 (during session): Cycle records are appended after each critique-respond-update turn.
     - Phase 2 (end of session): Summary Statistics and Evolution by Section are generated. -->

---

## Cycle 1: Initial Draft

### User Input
> The biggest assumption is that students have trouble when AI advice doesn’t match what they’re trying to build. I want to test whether checking the student’s goal first makes AI hints more helpful without making the interaction annoying.

### AI Draft Summary
The AI synthesized the user's input alongside the product thesis ([product-thesis.md](file:///Users/sanihasreedhara/Developer/skills/docs-plans/project-foundations/product-thesis.md)) and research thesis ([research-thesis.md](file:///Users/sanihasreedhara/Developer/skills/docs-plans/project-foundations/research-thesis.md)) into an initial `validation-plan.md` draft:
- **Core Hypotheses & Research Questions:** Structured 8 concise items across 4 categories (Context: C1, C2; Value: V1, V2; Design: D1, D2; Impact: I1, I2).
- **MVP / Protostudy Sequence:** Defined a 2-stage lean MVP sequence (MVP 1: Interactive WoZ / Scripted Verification Gate; MVP 2: Conditional Triggering Agent).
- **Timeline & Risks:** Outlined product/research risk priority order and a 2-phase learning timeline.

### What the AI added beyond what the user said
- **Four Category Hypothesis Structure:** Categorized the user's core intuition across Context, Value, Design, and Impact, connecting them directly to Cognitive Load Theory (Sweller) and Contingency Scaffolding (Wood).
- **Two-Stage MVP Sequencing:** Structured a progressive validation plan separating initial wizard-of-oz/scripted goal-checking (MVP 1) from automated query-gating heuristics (MVP 2).
- **Observables & Metrics:** Operationalized "helpful without being annoying" into explicit metrics: hint applicability rates, context-correction frequencies, override rates, and perceived interaction friction.

---

## Cycle 2: Sharpening Core Hypotheses with Mechanism & Metrics

### AI Critique
1. 🚨 **Falsifiable Mechanism in V1:** Pushed to restructure V1 using the **If/Then/Because** template to state exact cause, effect, and reduction metrics (>30% reduction in hint rejection rate).
2. ⚠️ **Explicit Kill Threshold in V2:** Pushed to define a clear kill threshold for interaction friction (>20% bypass/intrusiveness rating).
3. ⚠️ **Operationalizing Theory-Derived Metrics in I1:** Pushed to ground Sweller's Cognitive Load Reduction in 3 explicit observable metrics: context-correction follow-ups, hint deletion rates, and task resolution speed.

### User Response
> I agree with sharpening V1 using the If/Then/Because structure and making I1's measurements more specific. Please make those changes and keep the rest of the validation plan unchanged.

### Document Delta
| Field | Before | After |
|---|---|---|
| V1 (Hint Applicability) | Generic prediction statement | Formatted as If/Then/Because with explicit >30% hint rejection reduction signal |
| V2 (Friction Tolerance) | Open question framing | Added explicit kill threshold (>20% bypass/intrusiveness rating on routine tasks) |
| I1 (Cognitive Load) | General telemetry list | Operationalized into 3 specific metrics: (1) follow-up correction count, (2) hint deletion rate, (3) task resolution speed |

### What shifted
- Formatted V1 with explicit causal mechanism and quantitative signal.
- Established an explicit kill threshold for V2 friction tolerance.
- Operationalized I1 cognitive load reduction into concrete deployment metrics.

---

## Cycle 3: Conditioning MVP 2 Scope on MVP 1 Empirical Findings

### AI Critique
1. 🚨 **Dependency Rationale:** Pushed to clarify that the scope of MVP 2 (selective gating agent) must explicitly depend on empirical findings from MVP 1 rather than assuming complex gating heuristics are needed up front.

### User Response
> I agree that MVP 2 should depend on what we learn from MVP 1. However, please avoid framing this as a specific “friction threshold.” Instead, say that MVP 1 results will determine whether selective gating is necessary and how it should work. Please make that change and keep the rest of the plan unchanged.

### Document Delta
| Field | Before | After |
|---|---|---|
| MVP 2 Purpose | Validate automated triggering heuristics... | Validate automated triggering heuristics... Results from MVP 1 will directly determine whether selective gating is necessary at all and how its interaction mechanism should work. |
| Appendix: MVP Sequence | Empty | Added 🔵 **Strong Stance on MVP 2 Triggering Rationale** rejecting narrow "friction threshold" framing in favor of broader empirical dependency on MVP 1 findings. |

### What shifted
- Clarified that MVP 2's necessity and architecture depend directly on MVP 1 empirical findings.
- Logged a Strong Stance capturing the user's explicit framing preference in the Appendix.

---

## Cycle 4: Drafting Positionality Statement

### User Reflection
> I am an undergraduate student developer and also have firsthand experience using the Tech4Good AI coding agent that this project focuses on. Because I have personally experienced situations where AI guidance did not match my intended architecture, I may be more likely to notice or emphasize this problem. I also need to avoid assuming that other students experience the same issues or prefer the same type of AI interaction. During validation, I will treat my experience as a starting hypothesis and rely on student feedback and observed behavior rather than assuming my experience represents everyone.

### Document Delta
| Field | Before | After |
|---|---|---|
| Positionality Statement | Blank comment | Synthesized statement framing insider domain knowledge as an undergraduate developer while establishing explicit safeguards against confirmation bias. |

### What shifted
- Added researcher positionality acknowledging firsthand experience with the Tech4Good coding agent.
- Explicitly committed to using empirical telemetry and broad student interviews to test starting hypotheses rather than projecting personal preferences onto participants.

---

## Summary Statistics

| Metric | Count |
|---|---|
| Total interaction cycles | 4 |
| Times user narrowed scope | 2 |
| Times user corrected AI framing | 1 |
| Times user defended a choice against AI | 1 |
| Times user referenced specific document lines | 1 |
| Times AI forced a question that unlocked new thinking | 3 |
| Times AI filled gaps from user's existing knowledge | 2 |
| Times AI proposed text improvements user accepted | 3 |
| Largest single document delta | Cycle 1 (Structuring initial 4-category hypotheses and 2-stage MVP sequence) |

---

## Evolution by Section

### Core Hypotheses & Research Questions

**Initial state (from Cycle 1):**
The AI initially expanded the user's core intuition into 8 items across Context (C1, C2), Value (V1, V2), Design (D1, D2), and Impact (I1, I2).

**Evolution:**
- **Cycle 2:** Sharpened V1 using an If/Then/Because structure with an explicit >30% hint rejection reduction signal, added an explicit kill threshold to V2, and operationalized Sweller's Cognitive Load Reduction (I1) into 3 concrete telemetry metrics.

**AI critiques that drove change:**
> 1. 🚨 **Falsifiable Mechanism in V1:** Pushed to restructure V1 using the **If/Then/Because** template to state exact cause, effect, and reduction metrics.
> 2. ⚠️ **Operationalizing Theory-Derived Metrics in I1:** Pushed to ground Sweller's Cognitive Load Reduction in explicit observable metrics.

**User's voice through the evolution:**
> "I agree with sharpening V1 using the If/Then/Because structure and making I1's measurements more specific. Please make those changes and keep the rest of the validation plan unchanged."

**Final state:**
A set of 8 concise hypotheses and research questions spanning Context, Value, Design, and Impact, grounded in theoretical frameworks and measurable deployment telemetry.

---

### MVP / Protostudy Sequence

**Initial state (from Cycle 1):**
The AI structured a 2-stage MVP sequence (MVP 1: Scripted Intent Verification Probe; MVP 2: Selective Gating Agent).

**Evolution:**
- **Cycle 3:** Clarified that MVP 2's necessity and gating logic depend directly on empirical findings from MVP 1. Logged a Strong Stance in the Appendix capturing the user's preference for broad empirical dependency over a narrow "friction threshold."

**AI critiques that drove change:**
> 1. 🚨 **Dependency Rationale:** Pushed to clarify that the scope of MVP 2 must explicitly depend on empirical findings from MVP 1.

**User's voice through the evolution:**
> "I agree that MVP 2 should depend on what we learn from MVP 1. However, please avoid framing this as a specific “friction threshold.” Instead, say that MVP 1 results will determine whether selective gating is necessary and how it should work."

**Final state:**
A 2-phase MVP sequence with clear product and research risk priorities, milestone dates, and explicit dependency of MVP 2 on MVP 1 findings.
