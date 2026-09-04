# Calibrated AI Coding Mentor Validation Plan

<!-- Validation strategy for research-led social innovation projects. Core hypotheses and research questions define what we're trying to learn; the MVP/protostudy sequence defines how we learn it. Owned by /define-validation. Observable signals, interview instruments, and reflection protocols are developed per-MVP using /protostudy-prep. -->

This document provides the strategic overview of what we're validating, why, and in what order. It defines a series of protostudies to validate and derisk both the product and research aspects of the project. Detailed build plans, data collection instruments, and reflection protocols live in per-MVP protostudy documents.

---

## Core Hypotheses & Research Questions

What we're trying to learn, organized by categories that span our integrated approach — contextual understanding, product viability, design knowledge, and community impact. Each item concisely describes what the question/hypothesis is and why it matters to us. They will be fleshed out in more detail in the individual protostudy documents.

### Context: User & Ecosystem

Building a deeper understanding of the user and community ecosystem — surfacing insights about needs and contextual, systemic risks that shape what to design.

C1. **Goal-Advice Disconnect Friction** *(Open Question — MVP 1).* How do student developers currently recognize, react to, and resolve AI coding assistant hints that are plausible in isolation but misaligned with their intended architectural design direction? *Why it matters:* Establishes baseline diagnostic friction and determines whether students realize the AI misunderstood their goal or silently adopt misaligned code.

C2. **Uncommitted Design Direction Context** *(Open Question — MVP 1).* What portion of a student's active coding intent is captured in existing codebase artifacts (ASTs, open tabs, git history) versus existing only in uncommitted mental models or scratch documentation? *Why it matters:* Tests our fundamental premise that passive codebase indexing (RAG) cannot infer uncommitted design directions without active verification.

### Value: Product-Market Fit, Demand & Growth

Does the product solve a felt need, and will people adopt and spread it? These questions determine whether the solution is viable as a sustained offering.

V1. **Hint Applicability & Value Perception** *(Prediction — MVP 1).* If the AI agent states its goal interpretation prior to hint generation on architectural tasks, then student developers will abandon or context-correct significantly fewer hints (reducing hint rejection rate by >30%), because hints will align with their intended architecture rather than a plausible-in-isolation default. *If wrong:* Intent verification does not improve hint utility, indicating that retrieval accuracy or prompt quality is a higher priority bottleneck.

V2. **Conversational Friction Tolerance** *(Prediction + Open Question — MVP 1).* *Prediction:* Students will tolerate a brief 1-sentence goal verification pause on complex architectural queries if it prevents misguided debugging loops. *Kill threshold:* If >20% of goal verification pauses on routine tasks are bypassed or rated as intrusive, the mechanism requires tighter selective gating. *Open question:* At what point does pre-hint verification feel overly intrusive or "annoying," and how does friction tolerance vary by task complexity?

### Design: Embodiment & Experience

How users interpret and interact with the design — the design conjectures and experiential insights that shape the next design iteration and design theory.

D1. **Lightweight Goal Verification Triggers** *(Prediction + Open Question — MVP 2).* *Prediction:* Selective gating heuristics based on task ambiguity (e.g., state management, component integration queries) can trigger goal checks on architectural tasks while allowing direct responses for routine syntax queries. *Open question:* What interaction pattern (e.g., inline goal restatement vs explicit confirmation prompt) maximizes goal alignment with minimal interaction friction?

D2. **Goal Representation Clarity** *(Open Question — MVP 1).* How do students prefer the AI agent to state its understanding of their goal—e.g., structural component flow ("Updating goals via Signal store") vs high-level functional intent ("Adding goal persistence")—and how easily can they correct inaccurate interpretations?

### Impact: Mediating Processes & Outcomes

The deeper psychological and behavioral changes we hope to produce — the theoretical conjectures and the actual community impact we're striving for.

I1. **Diagnostic Cognitive Load Reduction** *(Prediction — MVP 1).* Stating goal interpretations before hint generation will reduce student diagnostic cognitive load (Sweller, 1988), operationalized by: (1) fewer context-correction follow-up messages per task, (2) lower rates of hint deletion/rejection, and (3) faster student resolution of architectural tasks. *If wrong:* The verification step adds extraneous processing load without reducing diagnostic overhead.

I2. **Metacognitive Goal Articulation** *(Prediction + Open Question — MVP 2).* *Prediction:* Being asked to confirm or correct AI goal interpretations encourages students to engage in metacognitive monitoring (Flavell, 1979), leading to clearer mental models of their own software architecture. *Open question:* Does goal verification help novices clarify their own design intentions when they were initially unsure of their approach?

---

## MVP / Protostudy Sequence

### Product Perspective

Evaluating whether intent verification solves a felt user problem without introducing unacceptable conversational friction. The key product risks, in priority order:

1. **Intrusiveness Risk** — Students find goal verification pauses tedious and prefer direct hints even if occasionally misaligned. If wrong, pre-generation verification is fundamentally unviable as a default interaction mode.
2. **Alignment Failure Risk** — Even when the agent states its goal interpretation, it fails to generate better hints because LLM reasoning remains flawed despite goal alignment. If wrong, intent verification does not solve hint quality issues.

### Research Perspective

Validating the theoretical mechanisms and selective gating heuristics. The key research risks, in the order we need to verify them:

1. **Diagnostic Overhead Risk (Sweller/Wood)** — Verifying intent actually reduces extraneous cognitive load compared to filtering misaligned hints post-hoc.
2. **Selective Gating Risk (Horvitz)** — Task-type heuristics can reliably separate high-uncertainty architectural queries (requiring verification) from low-uncertainty syntax queries (requiring direct answers).

### Timeline

Deploying within Tech4Good student development teams during active project sprints.

| Phase | Target Date | What Happens | What We Learn |
|---|---|---|---|
| MVP 1: Scripted Intent Verification Probe | Week 2 (Sept 15, 2026) | Deploy prompt-wrapped agent stating goal context before hint generation during live student coding sessions. | Baseline hint applicability, student reaction to goal restatements, and interaction friction boundaries (Addresses #C1, #V1, #V2, #D2, #I1). |
| MVP 2: Selective Gating Agent | Week 5 (Oct 6, 2026) | Deploy automated agent with conditional triggers (gating intent checks on architectural queries vs direct execution on syntax queries). | Effectiveness of selective gating heuristics, metacognitive impact, and long-term workflow integration (Addresses #C2, #D1, #I2). |

### MVP 1: Scripted Intent Verification Probe

**Purpose:** Test whether stating goal interpretations before hint generation improves hint applicability and reduces diagnostic cognitive load without annoying student developers. *(Addresses: C1 [Goal-Advice Disconnect], V1 [Hint Applicability], V2 [Friction Tolerance], D2 [Goal Representation], I1 [Cognitive Load])*

**What we build:** A lightweight scaffolding prompt wrapper around the existing Tech4Good coding agent. When a student requests assistance, the prompt wrapper generates a 1-sentence interpretation of the student's architectural goal ("It looks like you're trying to update the weekly goals state via the Signal store..."), and provides a hint based on that context. In MVP 1, goal restatements are always included for architectural tasks to test the core interaction mechanism with zero custom backend infrastructure.

**How we learn:** Deploy with 6–8 Tech4Good student developers during regular coding sessions. Collect log telemetry (hint acceptance/rejection, context correction messages, task completion time) and conduct post-session semi-structured debrief interviews focusing on perceived helpfulness vs interaction friction.

→ Detailed plan: *to be created via /protostudy-prep*

### MVP 2: Selective Gating Agent

**Purpose:** Validate automated triggering heuristics that selectively gate intent verification on architectural queries while allowing direct responses for syntax queries. Results from MVP 1 will directly determine whether selective gating is necessary at all and how its interaction mechanism should work. *(Addresses: C2 [Uncommitted Context], D1 [Selective Triggers], I2 [Metacognitive Articulation])*

**What we build:** An automated selective verification layer integrated into the lab's coding agent. Uses intent ambiguity heuristics (analyzing query complexity, component boundary references, and state modification scope) to decide whether to: (a) restate goal context and verify, or (b) provide a direct answer immediately.

**How we learn:** Multi-week deployment across 2–3 project teams. Log trigger frequency per query category, confirmation vs correction responses, override rates, and changes in student architectural self-efficacy over time.

→ Detailed plan: *to be created via /protostudy-prep*

---

## Positionality Statement

As an undergraduate student developer in Tech4Good with firsthand experience using the lab's AI coding agent, I bring insider domain knowledge regarding how students interact with scaffolding agents. Having personally experienced instances where AI guidance misunderstood my intended architecture, I am sensitized to the Intent-and-Context Alignment Gap. To mitigate confirmation bias, I explicitly treat my personal experience as a starting hypothesis rather than representative truth. Validation studies will rely on empirical telemetry (hint rejection rates, context-correction logs) and semi-structured debriefs across diverse student developers to evaluate whether others share these friction points and preferences.

---

## Appendix: Stances & Deferred Issues

### Core Hypotheses & Research Questions

### MVP / Protostudy Sequence

- 🔵 **Strong Stance on MVP 2 Triggering Rationale:** The user pushed back against framing the transition between MVP 1 and MVP 2 around a specific "friction threshold." Instead, the user specified that empirical findings from MVP 1 will determine more broadly whether selective gating is necessary at all and how its interaction mechanism should work.
