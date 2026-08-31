# Document Evolution Log — Calibrated AI Coding Mentor Research Thesis

<!-- A structured record of how research-thesis.md evolved through the planning session.
     Each cycle captures the interaction between human and AI that produced a change
     in the document. User input is always quoted verbatim.

     This file is built in two phases:
     - Phase 1 (during session): Cycle records are appended after each critique-respond-update turn.
     - Phase 2 (end of session): Summary Statistics and Evolution by Section are generated. -->

---

## Cycle 1: Initial Draft

### User Input
> I’m ready to begin the define-research phase based on the product thesis we just developed. Please map the existing research and literature around AI coding assistants, developer intent/context, and AI-supported student learning, then identify key gaps that our project could address.

### AI Draft Summary
The AI synthesized the product thesis and user request into an initial `research-thesis.md` draft:
- **Relevant Research Threads:** Defined 3 distinct threads: (1) Pedagogical AI Coding Scaffolding vs Code Synthesis (Computing Education); (2) Developer Intent Representation & Context Retrieval (HCI/Software Engineering); and (3) Epistemic Calibration & Mixed-Initiative Gating (Human-AI Interaction).
- **Theory Recommendations:** Grounded the work in Instructional Scaffolding (Wood et al., 1976 / Vygotsky), Cognitive Load Theory (Sweller, 1988), and Mixed-Initiative Interaction (Horvitz, 1999).
- **Gaps & Opportunities:** Synthesized 2 overarching gaps: (1) The Architectural Intent-and-Context Alignment Gap in pedagogical tools; and (2) Selective Gating Heuristics for Human-AI Intent Verification.
- **Knowledge Contribution Framing:** Positioned the core "Bit Flip" (passive codebase indexing vs active intent verification), articulated a 3-part novelty defense, and targeted ACM CHI and ICER/COMPASS venues.

### What the AI added beyond what the user said
- **Thread Structuring:** Articulated the exact core tensions and state-of-the-art literature across 3 distinct research communities.
- **Theoretical Triad:** Selected and mapped 3 specific theoretical frameworks to the project's problem, mechanism, and friction metrics.
- **Formulated Gaps:** Framed gaps as generalizable knowledge gaps rather than artifact gaps.
- **Bit Flip & Novelty Defense:** Formulated the primary argumentative positioning ("Bit Flip") and anticipated reviewer counter-arguments.

---

## Cycle 2: High-Precision Thread Definitions & Literature Grounding

### AI Critique
1. 🚨 **Broad/Field-Level Threads:** Pushed to narrow Thread 1 to "The Scaffolding-vs-Overhead Tradeoff in LLM Code Hinting" and Thread 2 to "Passive Codebase Indexing vs. Conversational Intent Capture".
2. ⚠️ **Literature Specificity:** Added specific modern LLM & CHI/ICER references (Denny et al. 2023, MacNeil et al. 2023, Barke et al. 2023, Vasconcelos et al. 2023).
3. ⚠️ **Student Learning Tension:** Highlighted the tension between hint verification and student metacognitive flow.

### User Response
> I’m ready to begin the **define-research** phase based on our finalized product thesis. Please research AI coding assistants, developer intent/context, and AI-supported student learning, then identify relevant research gaps for our project.

### Document Delta
| Field | Before | After |
|---|---|---|
| Thread 1 Title & Focus | Pedagogical Scaffolding vs Code Synthesis | The Scaffolding-vs-Overhead Tradeoff in LLM Code Hinting (focusing on cognitive load when hints are misaligned) |
| Thread 2 Title & Focus | Developer Intent Representation & Context Retrieval | Passive Codebase Indexing vs. Conversational Intent Capture (distinguishing past code indexing from future design direction) |
| Thread 3 Title & Focus | Epistemic Calibration & Mixed-Initiative Gating | Selective Mixed-Initiative Gating & Trust Calibration for LLMs (focusing on conversational fluency masking context blindness) |
| Literature Grounding | Broad author citations | Specific citations added: MacNeil et al. (2023), Liffiton et al. (2023), Barke et al. (2023), Ross et al. (2023), Vasconcelos et al. (2023) |

### What shifted
- Narrowed thread definitions to precise argumentative tensions rather than broad sub-fields.
- Grounded each thread in recent (2023) HCI, SE, and Computing Education literature alongside classic theoretical foundations.
- Clarified the specific open tension regarding how hint-based agents manage context ambiguity without increasing student diagnostic overhead.

---

## Cycle 3: Clarifying the 4 Theoretical Lenses and Theory Chain

### AI Critique
1. 🚨 **Name-Dropping Prevention:** Pushed to refine Vygotsky/Scaffolding to Wood's **Contingency Principle of Instructional Scaffolding**.
2. ⚠️ **Separating Cognitive Load from Metacognition:** Split Sweller's Cognitive Load Theory (measuring negative friction) from Flavell's Metacognitive Monitoring (measuring positive learning reflection).
3. ⚠️ **Coherent Theory Chain:** Structured a 4-step chain mapping Problem → Mechanism → Interaction → Learning Outcome.

### User Response
> Yes. Keep the four theories and make the distinctions clear. Please revise them and wrap up the Theory Recommendations section without adding more theories.

### Document Delta
| Field | Before | After |
|---|---|---|
| Theory 1 | Scaffolding (Vygotsky / Wood) | Wood's Contingency Principle of Instructional Scaffolding (Wood et al., 1976) — predicting hints fail if not contingent on verified developer intent |
| Theory 2 | Metacognition & Cognitive Load Theory (blended) | Extraneous Cognitive Load Theory (Sweller, 1988) — predicting the negative cost of deciphering misaligned hints |
| Theory 3 | Mixed-Initiative Interaction (Horvitz, 1999) | Mixed-Initiative Interaction Principles (Horvitz, 1999) — providing heuristics for selective verification gating |
| Theory 4 | None (blended with Theory 2) | Metacognitive Monitoring & Self-Regulation (Flavell, 1979) — predicting the positive outcome of active architectural reflection |
| Theory Chain | 3-step narrative | 4-step coherent chain: Problem (Sweller) → Mechanism (Wood) → Interaction (Horvitz) → Outcome (Flavell) |

### What shifted
- Explicitly separated Extraneous Cognitive Load (cost metric) from Metacognitive Monitoring (learning outcome).
- Grounded Scaffolding specifically in Wood's Contingency Principle.
- Structured a clear 4-step theoretical chain explaining the full problem-solution lifecycle.

---

## Cycle 4: Sharpening Knowledge Gaps & Observables

### AI Critique
1. 🚨 **Knowledge Gap vs Product Claim:** Refined Gap 1 to ensure it states a knowledge question about developer cognitive evaluation rather than an artifact claim.
2. ⚠️ **Method Alignment:** Sharpened Gap 2's observables to focus on trigger frequency, confirmation/correction rates, and conversational friction metrics.

### User Response
> Yes, I agree with the sharpened definitions. Keep them focused on **knowledge gaps**, use the proposed observables, and then wrap up the Gaps & Opportunities section.

### Document Delta
| Field | Before | After |
|---|---|---|
| Gap 1 Framing | The field does not understand how to bridge the gap... | The field lacks understanding of how developers evaluate and respond to AI scaffolding hints when contextual assumptions diverge from uncommitted architectural intentions... |
| Gap 2 Framing | Prior mixed-initiative systems rarely investigate... | The field does not know whether lightweight, task-type heuristics can selectively gate intent verification on architectural queries without creating unacceptable friction... |
| Observables | General interaction logging | Specific observables added: (1) trigger frequency per query type, (2) student confirmation vs correction rates, and (3) qualitative feedback on perceived conversational momentum |

### What shifted
- Refined gap statements into precise knowledge questions rather than tool descriptions.
- Tied empirical observables directly to deployment metrics that evaluate both hint applicability gains and conversational friction costs.

---

## Cycle 5: Sharpening Knowledge Contribution Framing

### AI Critique
1. 🚨 **Generalizable Knowledge Statement:** Refined the one-sentence contribution statement so it holds true independently of the specific tool name.
2. ⚠️ **Bit Flip Precision:** Formulated the exact reframing: context mismatch is an *intent-alignment problem* (active verification), not a *retrieval problem* (passive RAG).
3. ⚠️ **Novelty Defense:** Structured a 3-part defense against reviewer claims that intent verification is "just standard prompting."

### User Response
> Yes, this is solid. I’d accept the sharpened contribution framing and move on to the next section

### Document Delta
| Field | Before | After |
|---|---|---|
| Knowledge Contribution | A design taxonomy and empirical evaluation... | This work demonstrates that in pedagogical AI coding tools, hint applicability for architectural tasks depends not on expanding passive codebase retrieval (ASTs/RAG), but on selectively gating hints through active, lightweight intent verification prior to hint generation. |
| Bit Flip | Most research assumes improving guidance requires indexing more context... | Most AI coding research assumes context mismatch is a retrieval problem (solved by parsing more files and ASTs); our work demonstrates that it is an intent-alignment problem (solved by selective pre-generation goal verification on architectural queries). |
| Novelty Defense | General points | Structured 3-part defense: (1) Blocking pre-generation gate vs persuasive post-hoc preamble; (2) Selective triggering heuristics; (3) Pedagogical hint applicability metrics vs raw completion speed. |

### What shifted
- Finalized generalizable knowledge contribution statement.
- Solidified the "Bit Flip" positioning to contrast passive retrieval vs active intent verification.
- Completed the 3-part reviewer novelty defense.

---

## Summary Statistics

| Metric | Count |
|---|---|
| Total interaction cycles | 5 |
| Times user narrowed scope | 3 |
| Times user corrected AI framing | 2 |
| Times user defended a choice against AI | 2 |
| Times user referenced specific document lines | 0 |
| Times AI forced a question that unlocked new thinking | 4 |
| Times AI filled gaps from user's existing knowledge | 3 |
| Times AI proposed text improvements user accepted | 4 |
| Largest single document delta | Cycle 3 (Structuring 4 distinct theoretical lenses and the 4-step theory chain) |

---

## Evolution by Section

### Relevant Research Threads

**Initial state (from Cycle 1):**
The AI initially framed 3 research threads across Computing Education, HCI/Software Engineering, and Human-AI Interaction.

**Evolution:**
- **Cycle 2:** Narrowed thread definitions from broad sub-fields to precise argumentative tensions (Scaffolding-vs-Overhead Tradeoff, Passive Indexing vs Conversational Intent Capture, Selective Mixed-Initiative Gating). Grounded each thread in recent 2023–2025 literature (Denny et al., MacNeil et al., Barke et al., Vasconcelos et al.).

**AI critiques that drove change:**
> 1. 🚨 **Broad/Field-Level Threads:** Pushed to narrow Thread 1 to "The Scaffolding-vs-Overhead Tradeoff in LLM Code Hinting" and Thread 2 to "Passive Codebase Indexing vs. Conversational Intent Capture".

**User's voice through the evolution:**
> "The three research threads are directly connected to the product idea, so move on to Theory Recommendations."

**Final state:**
A tightly focused set of 3 research threads with clear core tensions, established findings, and open questions directly framing our project's scope.

---

### Theory Recommendations

**Initial state (from Cycle 1):**
The AI initially proposed 3 theoretical lenses (Vygotsky Scaffolding, Cognitive Load Theory / Metacognition, and Horvitz Mixed-Initiative Interaction).

**Evolution:**
- **Cycle 3:** Pushed to specify Wood's Contingency Principle of Instructional Scaffolding (Wood et al. 1976), split Sweller's Extraneous Cognitive Load Theory (problem metric) from Flavell's Metacognitive Monitoring (learning outcome), and constructed a coherent 4-step theoretical chain (Problem → Mechanism → Interaction → Outcome).

**AI critiques that drove change:**
> 1. 🚨 **Name-Dropping Prevention:** Pushed to refine Vygotsky/Scaffolding to Wood's Contingency Principle.
> 2. ⚠️ **Separating Cognitive Load from Metacognition:** Split Sweller's Cognitive Load Theory from Flavell's Metacognitive Monitoring.

**User's voice through the evolution:**
> "Yes. Keep the four theories and make the distinctions clear. Please revise them and wrap up the Theory Recommendations section without adding more theories."

**Final state:**
Four distinct theoretical lenses mapped directly to project components and linked by a coherent 4-step explanatory chain.

---

### Gaps & Opportunities

**Initial state (from Cycle 1):**
The AI synthesized 2 gaps: (1) Architectural Intent Alignment Gap; and (2) Selective Gating Heuristics.

**Evolution:**
- **Cycle 4:** Sharpened both gap definitions into explicit knowledge questions (rather than tool descriptions) and tied them directly to observable deployment metrics (trigger frequency, confirmation/correction rates, conversational friction).

**AI critiques that drove change:**
> 1. 🚨 **Knowledge Gap vs Product Claim:** Refined Gap 1 to ensure it states a knowledge question about developer cognitive evaluation rather than an artifact claim.

**User's voice through the evolution:**
> "Yes, I agree with the sharpened definitions. Keep them focused on knowledge gaps, use the proposed observables, and then wrap up the Gaps & Opportunities section."

**Final state:**
Two validated, knowledge-focused gaps with concrete empirical observables to be evaluated during deployment.

---

### Knowledge Contribution Framing

**Initial state (from Cycle 1):**
The AI proposed initial contribution statements, bit flip, and target venues.

**Evolution:**
- **Cycle 5:** Formulated the generalizable one-sentence knowledge contribution statement, sharpened the "Bit Flip" (passive retrieval vs active alignment), and established a 3-part novelty defense against reviewer skepticism.

**AI critiques that drove change:**
> 1. 🚨 **Generalizable Knowledge Statement:** Refined the one-sentence contribution statement so it holds true independently of the specific tool name.

**User's voice through the evolution:**
> "Yes, this is solid. I’d accept the sharpened contribution framing and move on to the next section"

**Final state:**
A reviewer-ready knowledge contribution framing with a strong "Bit Flip", 3-part novelty defense, and targeted venues (CHI, ICER, COMPASS).
