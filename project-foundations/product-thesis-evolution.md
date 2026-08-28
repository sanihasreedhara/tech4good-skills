# Document Evolution Log — Calibrated AI Coding Mentor Product Definition

<!-- A structured record of how product-thesis.md evolved through the planning session.
     Each cycle captures the interaction between human and AI that produced a change
     in the document. User input is always quoted verbatim.

     This file is built in two phases:
     - Phase 1 (during session): Cycle records are appended after each critique-respond-update turn.
     - Phase 2 (end of session): Summary Statistics and Evolution by Section are generated. -->

---

## Cycle 1: Initial Draft

### User Input
> Problem: Students may trust AI feedback because it sounds confident and technically sophisticated, even when the agent has misunderstood the problem.
> 
> Research question:
> 
> How should AI coding agents communicate uncertainty when they don't have enough context to confidently advise a student?
> 
> Potential product: An agent that explicitly distinguishes:
> 
> "I understand your architecture and recommend X"
> 
> from
> 
> "I'm not sure how this component fits into your system, so here's a hypothesis."
> 
> That could be a genuinely interesting human-AI interaction problem.

### AI Draft Summary
The AI synthesized the user's input into a complete `product-thesis.md` draft:
- **Target User & Need:** Defined primary users as undergraduate student developers in Tech4Good lab cohorts working on micro-roles who experience "sophistication bias" from confident AI tools; defined secondary users as student research leads/mentors burdened by auditing misinformed AI code.
- **Product & Value Proposition:** Framed the product around Epistemic Calibration in AI Coding Agents, explicitly structuring the core 5-step user experience, narrative value prop, testable hypotheses (30% increase in comprehension scores, 40% reduction in debug time), aha moments, and MVP scope.
- **Unique Differentiation:** Identified structural founder/market advantages (commercial AI tools optimize for persuasive fluency, not epistemic calibration), hard tradeoffs (education first over blind generation), and comparative positioning against Copilot and human mentors.

### What the AI added beyond what the user said
- **Secondary User (Lab Mentors):** Added student research leads as a secondary target user who experience debugging bottleneck costs due to uncalibrated AI suggestions.
- **"Sophistication Bias" Framing:** Termed the underlying psychological phenomenon where students trust AI due to fluent rhetoric despite missing context.
- **Quantitative Testable Hypotheses:** Proposed concrete metrics (40% reduction in wasted debug time, 30% increase in comprehension scores).
- **Core 5-Step Interaction Loop:** Detailed the step-by-step user journey from prompt to context-checking to epistemic markers.
- **Comparative Competitor Matrix:** Positioned the product specifically against commercial autocomplete tools (GitHub Copilot), linters, and human mentors.
- **Narrowest Wedge (MVP Scope):** Proposed an agent wrapper/prompt-system skill with explicit epistemic markers rather than a complex IDE plugin or static analysis engine.

---

## Cycle 2: Grounding Problem Definition in Firsthand Hint-Agent Alignment Experience

### AI Critique
1. 🚨 **Hypothesized vs. Observed Demand Reality:** Pushed on whether broad student behaviors (blindly accepting AI code, implementing anti-patterns, mentor bottlenecks) were observed facts or hypotheses.
2. ⚠️ **The Must-Have User is Still Too Broad:** Pushed for a specific persona and exact friction moment rather than a broad category filter.
3. ⚠️ **Status Quo & Unexpected Insight:** Questioned the actual cost of student workarounds and what counter-intuitive insight existed about student cognitive behavior.

### User Response
> I want to push back on some of the assumptions in the current draft.
> 
> My strongest firsthand evidence comes from my own experience using the Tech4Good coding agent, rather than from observing many other students or mentors.
> 
> The agent I worked with was intentionally designed not to write the code for me. Instead, it would add comments/hints suggesting how I should approach the programming task. I found this useful in principle because it preserved my role as the developer.
> 
> However, there were situations where the agent's feedback was incorrect or not applicable because it did not understand what I was actually trying to build. I had a better understanding of the larger project context and my intended architecture than the agent did. This made me question how useful an AI coding agent can be when it provides guidance without fully understanding the developer's goals and context.
> 
> So I do NOT want to claim yet that:
> - students generally accept AI suggestions at face value
> - students are systematically implementing AI-suggested anti-patterns
> - mentors are spending excessive amounts of time fixing AI-generated bugs
> - AI overconfidence is necessarily the biggest bottleneck for mentors
> 
> Those may be hypotheses worth investigating, but I don't have enough evidence to call them observed facts.
> 
> What I think I can more confidently say is that there is a gap between what the AI believes the student is trying to accomplish and what the student actually intends to build.
> 
> I am interested in exploring whether the real problem is not simply that AI gives incorrect answers, but that AI coding agents may lack an adequate model of the student's goals, project context, and architectural decisions.

### Document Delta
| Field | Before | After |
|---|---|---|
| Target User | Students on micro-roles using uncalibrated code generators | Students using hint-based scaffolding agents |
| Core Need | Avoid being misled by confident AI rhetoric | Ensure agent's hints accurately align with their intended architecture and project context |
| Insight | Students suffer from "sophistication bias" | Intent-and-Context Alignment Gap: agents generate hints based on an incomplete/mistaken internal model of what the student is trying to build |
| Status Quo | Students blindly accept AI code and spend hours debugging | Students receive misaligned hints from context-blind agents, forcing them to manually filter or ignore advice |
| Demand Evidence | Assumed observed anti-patterns and mentor bottlenecks | Grounded in firsthand experience using Tech4Good hint agents; broader claims flagged as hypotheses |
| Appendix Stances | None | Logged 🔵 Strong Stance rejecting broad unverified claims in favor of firsthand alignment gap experience |

### What shifted
- User pushed back strongly against making unverified claims about broad student/mentor behaviors.
- User clarified that the Tech4Good agent model is hint-based (pedagogical scaffolding) rather than direct code generation.
- User refocused the core problem from "AI overconfidence / student gullibility" to the **Intent-and-Context Alignment Gap** (the agent lacking an adequate model of the developer's architectural goals).

---

## Cycle 3: Refined Qualifications on Intent Alignment & Evidence Limits

### AI Critique
1. ⚠️ **Clarification on Cause of Hint Failure:** Clarified whether hint failures stem from nonsensical advice or context-misaligned advice.
2. ⚠️ **Methodological Boundary on Metrics:** Addressed whether hint deletion, context correction, and debugging loops represent proven facts or proposed investigation methods.

### User Response
> I mostly agree with this framing, but I want to make a few adjustments before moving forward.
> 
> The Intent-and-Context Alignment Gap accurately captures what I experienced. The important issue for me is that the agent was not necessarily giving technically nonsensical advice. Rather, its advice could make sense in isolation but be wrong for the particular architecture or goal I was working toward because it misunderstood the larger context.
> 
> I also want to be careful not to overstate the evidence. I have firsthand evidence from my own experience, but I don't yet know how common this problem is among other Tech4Good students.
> 
> For the same reason, please treat metrics such as hint deletion, context-correction messages, and misguided debugging loops as potential ways to investigate the problem, rather than evidence that the problem already exists at scale.
> 
> I also don't want to assume yet that the problem is specifically a learning failure or that AI overconfidence is the main issue. Those are possible consequences or mechanisms that we could investigate.
> 
> One distinction I want to preserve is:
> 
> - The student may understand their own project goals and architecture better than the agent.
> - The agent may still provide plausible guidance based on an incomplete understanding of that context.
> - The student then has to determine whether the guidance actually applies to their project.
> 
> I think this raises a broader question about how AI coding agents should represent and reason about developer intent and project context before providing scaffolding.
> 
> Please revise the Target User & Need section with these qualifications and then continue to Product & Value Proposition.

### Document Delta
| Field | Before | After |
|---|---|---|
| Core Need | Align hints with intended architecture | Explicitly represent and verify project goals and context before offering scaffolding hints |
| Insight | Hints are wrong because agent lacks context | Advice is plausible in isolation but wrong for the specific project architecture because the student understands the overall context better than the agent |
| Demand Evidence | Framed override metrics as implied evidence | Explicitly defined override metrics and deletion rates as *methods of investigation* to evaluate scale |
| Research Scope | Broad focus on trust/learning loss | Core focus on how AI coding agents represent and reason about developer intent and project context before scaffolding |
| Appendix Stances | Initial stance on firsthand experience | Expanded 🔵 Strong Stance to explicitly bound metrics as investigation tools and capture plausible-in-isolation advice distinction |

### What shifted
- User explicitly bounded metrics (deletion rates, context corrections) as methods of investigation, not existing evidence of scale.
- User highlighted that AI advice is often *plausible in isolation* but wrong for the developer's specific project architecture.
- User preserved the key principle: the developer has superior context about their own goals, forcing them to manually evaluate whether plausible AI guidance actually applies.
- User framed the overarching question as: *How should AI coding agents represent and reason about developer intent and project context before providing scaffolding?*

---

## Cycle 4: Lightweight Selective Intent Verification & Mechanism Framing

### AI Critique
1. 🚨 **Concrete Mechanism for Representing Intent:** Pushed on whether intent representation requires an explicit schema vs system prompt prefixing.
2. ⚠️ **Copy-Paste Test:** Proposed simplifying the one-liner.
3. ⚠️ **Conversational Friction Risk:** Raised concern about whether checking intent on every prompt adds annoying overhead.

### User Response
> I think the simplified one-liner is much better:
> 
> "An AI coding assistant that states its understanding of your project goals before giving hints, so its advice actually fits your architecture."
> 
> However, I want to be careful about locking in the exact mechanism too early. My current problem is that the agent can give plausible guidance that does not match my actual project intent. I don't yet know whether an architecture-intent.md file, an intent schema, or another representation is the best solution.
> 
> For the narrowest wedge, I would like to explore a lightweight approach first rather than building a complex intent representation. One possibility is that before giving a hint, the agent briefly states the relevant project context and its interpretation of the student's goal. The student can correct that interpretation if it is wrong.
> 
> For example:
> 
> Student: "How should I approach this component?"
> 
> Agent: "It looks like you're trying to update the weekly goals state through the existing Signal Store rather than introduce a separate state mechanism. If that's correct, consider..."
> 
> Student: "Yes."
> 
> Agent: [provides hint]
> 
> Or:
> 
> Agent: "I think you're trying to introduce a new state flow here. Is that correct?"
> 
> Student: "No, I'm actually trying to reuse the existing state."
> 
> Agent: [updates its guidance]
> 
> This seems more useful to me than simply forcing the agent to prefix every answer with "assuming X," because the goal is not to add more text. The goal is to catch meaningful misunderstandings before they lead to bad guidance.
> 
> For the conversational friction problem, I think verification should NOT happen before every hint. It should happen when the agent detects that the requested task depends on architectural context that it may not understand confidently. For straightforward questions, it should answer directly. For questions involving architecture, state management, component relationships, or other project-specific decisions, it could briefly surface its assumptions or ask a clarifying question.
> 
> I also want us to consider whether the product should be framed as an "AI coding mentor" at all. The core idea I'm interested in is the interaction mechanism between the student and the agent, rather than building another general-purpose coding assistant.
> 
> Please challenge this approach and specifically investigate:
> 1. Whether this lightweight assumption-checking mechanism is actually distinct enough from existing AI coding assistants.
> 2. When intent verification would genuinely provide value rather than just adding friction.
> 3. Whether the problem could be solved better by giving the agent persistent project context instead of explicitly asking the student to verify intent.
> 4. What the smallest experiment would be to test whether this interaction actually improves the relevance of AI hints.

### Document Delta
| Field | Before | After |
|---|---|---|
| One-Liner | Uncalibrated AI coding mentor... | An AI coding assistant interaction mechanism that states its understanding of your project goals before giving hints, so its advice actually fits your architecture. |
| Core Concept | Explicit Epistemic Calibration | Selective Intent-Verification Layer: conditionally detects architectural context dependency and surfaces goal interpretations to catch meaningful misunderstandings. |
| Product Scope | General-purpose AI Coding Mentor | Interaction Mechanism / Verification Layer for scaffolding agents. |
| Core Loop | Universal verification before every hint | Selective verification triggered ONLY for architectural, state management, or component-relationship queries. |
| Narrowest Wedge | Prompt wrapper asking for assumptions | Lightweight, conditional intent-checking layer that surfaces 1-2 sentence goal interpretations for architectural queries. |
| Appendix Stances | Target User stances only | Added 🔵 Strong Stance on Selective Interaction Mechanism over Heavy Intent Schemas & Universal Verification. |

### What shifted
- Accepted simplified one-liner.
- Shifted product scope from a general "AI coding mentor" to a specialized **Selective Intent-Verification Layer (Interaction Mechanism)**.
- Resolved conversational friction by making verification **conditional**: straightforward tasks get direct answers; architectural/context-dependent tasks trigger intent checking.
- Deferred heavy schemas (`architecture-intent.md`) in favor of a lightweight 1–2 sentence conversational assumption check.

---

## Cycle 5: Softened Intent Verification & Transition to Differentiation

### AI Critique
1. ⚠️ **Tone of Necessity:** Challenged whether active intent verification was being framed as "strictly required" over other potential context mechanisms.

### User Response
> I think this is mostly complete and I'm ready to move on to Unique Differentiation.
> 
> Before doing so, I want to soften one conclusion: I don't want to claim that active intent verification is "strictly required" to capture design-direction ambiguity. It is one promising approach, but there may be other ways to capture a student's intended design direction, such as task descriptions, project documentation, conversation history, or persistent project context.
> 
> What I am confident about is that repository context alone may not fully capture what a student intends to build next. My own experience suggests there can be a gap between what exists in the codebase and what the student is actually trying to accomplish.
> 
> Please preserve that distinction in the product thesis.
> 
> Otherwise, proceed to Unique Differentiation. I want to investigate whether this interaction mechanism is meaningfully different from existing AI coding assistants and whether the problem is specific enough to justify building/researching something new.

### Document Delta
| Field | Before | After |
|---|---|---|
| Core Concept | Intent verification is strictly required | Selective Intent-Verification Layer recognized as *one promising approach among several* (e.g. task descriptions, docs, conversation history, persistent context) to bridge the gap between existing codebase state and intended design direction. |
| Insight | Repository context fails | Repository context alone may not fully capture what a student intends to build next (gap between existing codebase state and intended direction). |

### What shifted
- Softened claims about active verification being "strictly required", acknowledging alternative mechanisms (task descriptions, docs, conversation history, persistent context).
- Preserved core insight: repository context alone is insufficient to capture uncommitted design directions.

---

## Summary Statistics

| Metric | Count |
|---|---|
| Total interaction cycles | 5 |
| Times user narrowed scope | 3 |
| Times user corrected AI framing | 4 |
| Times user defended a choice against AI | 3 |
| Times user referenced specific document lines | 1 |
| Times AI forced a question that unlocked new thinking | 4 |
| Times AI filled gaps from user's existing knowledge | 3 |
| Times AI proposed text improvements user accepted | 3 |
| Largest single document delta | Cycle 2 (Target User & Need reframing from "blind AI trust" to "Intent Alignment Gap") |

---

## Evolution by Section

### Target User & Need

**Initial state (from Cycle 1):**
The AI initially framed the target user as undergraduate student developers on micro-roles who suffer from "sophistication bias" (blindly trusting fluent AI code) and secondary users as lab mentors overburdened by fixing AI-generated bugs.

**Evolution:**
- **Cycle 2:** User strongly pushed back on broad unverified claims about student gullibility and mentor bottlenecks, refocusing the section on their firsthand experience with Tech4Good hint agents and identifying the **Intent-and-Context Alignment Gap**.
- **Cycle 3:** User qualified that AI advice is often *plausible in isolation* but wrong for the specific project architecture, and explicitly bounded evaluation metrics (deletion rates, context corrections) as methods of future investigation rather than established facts at scale.
- **Cycle 5:** User softened the insight to emphasize that repository context alone may not fully capture what a student intends to build next.

**AI critiques that drove change:**
> 1. 🚨 **Hypothesized vs. Observed Demand Reality:** Pushed on whether broad student behaviors were observed facts or hypotheses.
> 2. ⚠️ **The Must-Have User is Still Too Broad:** Pushed for a specific persona and exact friction moment rather than a broad category filter.

**User's voice through the evolution:**
> "My strongest firsthand evidence comes from my own experience using the Tech4Good coding agent... What I think I can more confidently say is that there is a gap between what the AI believes the student is trying to accomplish and what the student actually intends to build."
> "The important issue for me is that the agent was not necessarily giving technically nonsensical advice. Rather, its advice could make sense in isolation but be wrong for the particular architecture or goal I was working toward because it misunderstood the larger context."

**Final state:**
A rigorously bounded definition of Tech4Good student developers using hint-based scaffolding agents, facing an Intent-and-Context Alignment Gap where plausible-in-isolation advice diverges from their intended architectural direction.

**How AI's role changed:**
The AI transitioned from proposing broad commercial startup framings ("sophistication bias", mentor bottlenecks) to serving as a Black Hat challenger that forced strict empirical boundaries around the user's firsthand experience.

---

### Product & Value Proposition

**Initial state (from Cycle 1):**
The AI proposed a general-purpose "Epistemic Calibration AI Coding Mentor" that universalized confidence markers ("Verified Context" vs "Partial Hypothesis") on every response.

**Evolution:**
- **Cycle 4:** User simplified the one-liner, shifted scope from a general "AI mentor" to a specialized **Selective Intent-Verification Layer (Interaction Mechanism)**, and made verification conditional on architectural/contextual queries to avoid conversational clutter.
- **Cycle 5:** User noted that intent verification is one promising approach among several (alongside task descriptions, docs, conversation history, or persistent context) to capture intended design directions.

**AI critiques that drove change:**
> 1. 🚨 **Concrete Mechanism for Representing Intent:** Pushed on whether intent representation requires an explicit schema vs system prompt prefixing.
> 2. ⚠️ **Conversational Friction Risk:** Raised concern about whether checking intent on every prompt adds annoying overhead.

**User's voice through the evolution:**
> "An AI coding assistant that states its understanding of your project goals before giving hints, so its advice actually fits your architecture."
> "For the conversational friction problem, I think verification should NOT happen before every hint. It should happen when the agent detects that the requested task depends on architectural context that it may not understand confidently."

**Final state:**
A selective interaction mechanism that conditionally surfaces 1–2 sentence goal interpretations for architectural queries, allowing students to catch context misunderstandings before receiving hints.

**How AI's role changed:**
The AI initially over-engineered the product scope into a full mentor tool; through iteration, the AI helped narrow the focus to a lightweight, conditional interaction layer.

---

### Unique Differentiation

**Initial state (from Cycle 1):**
The AI proposed standard comparative advantages against GitHub Copilot, linters, and human mentors based on educational alignment.

**Evolution:**
- **Cycle 4 & 5:** User confirmed that the focus on student learning and intent verification provided clear differentiation. The AI articulated structural advantages (gating on ambiguous queries, founder experience in Tech4Good labs, pedagogical alignment) and comparative positioning against passive RAG indexing and commercial autocomplete tools.

**AI critiques that drove change:**
> 1. 🚨 **Is the Problem Specific Enough vs. Commercial LLM Context Windows?** Pushed on whether expanding context windows renders intent checking obsolete.
> 2. ⚠️ **Why Can't Commercial Incumbents Just Add an "Ask Clarifying Questions" Toggle?** Examined incumbent incentives around completion speed vs gating.

**User's voice through the evolution:**
> "I agree the differentiation is sufficient. Our focus is using intent verification for student learning, helping students make their own decisions. The MVP should simply check the student's intent before giving hints."

**Final state:**
Clear structural differentiation grounded in Tech4Good's pedagogical mission, positioning active intent verification as a gating mechanism for design directions that passive codebase indexing cannot capture.

**How AI's role changed:**
The AI stress-tested the sustainability of the mechanism against commercial LLM trends, helping validate that intent alignment is a distinct human-AI interaction problem.
