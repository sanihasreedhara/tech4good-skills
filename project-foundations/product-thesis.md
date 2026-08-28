# Calibrated AI Coding Mentor Product Thesis

<!-- Target User & Need, Product & Value Proposition, and Unique Differentiation. Owned by /define-product -->

<!-- This section defines who the product is for, what it does, and why it needs to exist. It covers the target user, the core problem, the solution, and the unique value proposition. -->

## Target User & Need

### 1. Student Developers in Tech4Good (Primary)
- **Target User:** Undergraduate student developers working on software projects (e.g., Tech4Good lab web applications) using hint-based AI coding agents that provide scaffolding (via comments, suggestions, or hints) rather than generating code directly.
- **Core Need:** Need AI coding agents to explicitly represent, reason about, and align with their project goals and intended architecture before offering scaffolding hints—so guidance is relevant to their specific project rather than just plausible in isolation.
- **Insight:** The core challenge is an **Intent-and-Context Alignment Gap**. Repository context alone may not fully capture what a student intends to build next—there is often a gap between existing codebase state and the student's intended design direction. When an agent provides hints based strictly on existing code or incomplete context, the advice may be plausible in isolation but inapplicable to the student's specific project goals.
- **Status Quo:** Students receive plausible AI hints that misinterpret their specific design intent or architecture, leaving them to manually assess applicability, re-explain project context, or ignore the hints.
- **Demand Evidence:**
  - *Observed:* Firsthand student experience in Tech4Good where a hint-based coding agent provided suggestions that were plausible in general but incorrect for the specific project architecture and intended goals.
  - *Hypothesized:* Other student developers using hint-based scaffolding agents experience similar friction where agent advice diverges from their project context—a hypothesis to be investigated through metrics like hint override rates and dialogue context corrections.
- **Must-Have User:** A student developer working on a non-trivial feature who has an intended architectural plan for their code, but receives plausible yet context-blind scaffolding hints from an agent.
  - *Why them specifically:* They have enough project awareness to spot when an agent's advice fails to account for their specific architectural goals, making the context gap immediately apparent.
  - *Access:* Direct access within Tech4Good research lab cohorts using experimental coding agents.

### 2. Tech4Good Lab Mentors & Tool Designers (Secondary)
- **Target User:** Mentors and researchers designing pedagogical AI coding agents and guiding student developer teams.
- **Core Need:** Understand how AI coding agents should represent and reason about developer intent and project context before offering scaffolding hints.
- **Insight:** Scaffolding agents intended to support learning are constrained by their ability to model the developer's goals and project state; ungrounded hints create cognitive friction regardless of how well-written the hints are.
- **Status Quo:** Tool designers build hint agents with generic prompts, while mentors observe students filtering through AI suggestions of varying applicability.
- **Demand Evidence:**
  - *Observed:* Lab commitment to developing pedagogical AI tools that preserve student agency rather than auto-generating code.
  - *Hypothesized:* Mentors and tool designers seek principles for how agents should check context and represent developer intent before giving advice.
- **Must-Have Customer:** Research leads building and evaluating AI scaffolding workflows for lab environments.
  - *Why them specifically:* They are actively seeking frameworks for effective human-AI co-reasoning in software development.
  - *Access:* Tech4Good lab leads and HCI research teams.

## Product & Value Proposition
- **One-Liner:** An AI coding assistant interaction mechanism that states its understanding of your project goals before giving hints, so its advice actually fits your architecture.
- **Core Concept:** Selective Intent-Verification Layer — An interaction mechanism for AI scaffolding agents that conditionally detects when a requested task depends on ambiguous architectural or project context, and briefly surfaces its goal interpretation to catch meaningful misunderstandings before providing hints. (Recognized as one promising approach among several—such as task descriptions, docs, or persistent context—to address the gap between existing codebase state and intended design direction.)
- **Core Experience:**
  1. The student asks the agent for assistance or scaffolding on a coding task.
  2. The agent evaluates the task type: straightforward syntax/logic tasks are answered directly; architectural, state management, or component-relationship tasks trigger context verification.
  3. For context-dependent tasks, the agent briefly states its interpretation of the student's architectural goal (e.g., *"It looks like you're trying to update state through the existing Signal Store rather than a new store. Is that correct?"*).
  4. If correct, the student confirms and receives targeted guidance; if incorrect, the student briefly corrects the intent, and the agent updates its internal context model.
  5. The agent delivers scaffolding hints grounded in the verified architectural intent.
- **Value Proposition:**
  - *Narrative:* Student developers receive AI hints that actively respect and align with their intended architecture, catching context misunderstandings *before* they result in misaligned guidance—without introducing unnecessary conversational clutter on simple tasks.
  - *Testable hypothesis:* Selective intent-verification before generating architectural hints will significantly reduce the proportion of plausible-yet-misaligned AI hints and decrease student context-correction overhead.
- **Aha Moments:**
  - *Student Developers (first aha):* The agent catches a wrong architectural assumption upfront (e.g. assuming a new state store when the project reuses an existing one), saving the student from following misaligned advice.
  - *Student Developers (sustained aha):* The agent knows when to answer directly vs. when to pause and check architectural alignment.
  - *Lab Mentors (first aha):* Observing students successfully use intent-calibrated agents to reason through complex architectural decisions without being led down wrong paths.
- **Narrowest Wedge (MVP):**
  - *Included:* A lightweight, conditional intent-checking layer that detects architectural/contextual queries, surfaces the agent's goal interpretation in 1–2 sentences, and updates hints based on student confirmation or correction.
  - *Excluded (future expansion):* Heavy intent schema databases (`architecture-intent.md`), full AST dependency graph parsers, multi-file static analysis tools.

## Unique Differentiation
- **Structural Advantages:**
  - *Founder Advantage:* Direct experience as student developers in Tech4Good navigating hint-based scaffolding agents on real research codebases.
  - *Market Advantage:* Commercial AI coding tools (Copilot, Cursor) optimize for rapid code auto-completion and engagement metrics; Tech4Good focuses on pedagogical human-AI interaction mechanisms and intent alignment for real-world learning.
  - *Product Advantage:* Explicit intent-verification gating on ambiguous architectural queries rather than unverified code/hint generation.
  - *Acquisition Advantage:* Native integration into Tech4Good lab agent workflows and CauseWay platform.
  - *Network Effects:* Logging intent-clarification interaction cycles produces generalizable design principles and heuristics for intent modeling in educational coding agents.
- **Hard Tradeoffs:**
  - *Not a general-purpose coding assistant:* Focuses strictly on the interaction mechanism for context verification, not on building an all-in-one IDE or code generator.
  - *Verification before execution on complex tasks:* Intentionally introduces a brief confirmation pause on architectural queries rather than providing unverified, instant answers.
- **Sustainability & Moat:**
  - *Why incumbents can't easily copy:* Commercial AI vendors face strong incentives to maximize instant completion speed and minimize conversational friction; they avoid adding gating steps or questioning user intent.
- **Future-Fit Thesis:** As AI systems become more capable at isolated code synthesis, the central human-AI interaction problem shifts from code generation to communicating, verifying, and aligning architectural intent.
- **Comparative Positioning:**
  - *vs. Commercial AI Autocomplete (Copilot/Cursor):* Autocomplete tools guess context implicitly from surrounding files and output code directly, frequently misinterpreting uncommitted design directions.
  - *vs. Standard Prompting Preamble:* Standard preambles explain *why* the AI chose code after generation; this mechanism acts as an explicit *blocking gate* before hint generation.
  - *vs. Passive Context Indexing (RAG/Vector DBs):* Passive context captures existing code (the past); intent verification surfaces the developer's intended design direction (the future).
- **Pricing Model:** Free and open-source for academic and social impact research labs (hypothesized).

## Appendix: Product Definition

### Target User & Need

- 🔵 **Strong Stance: Grounding Problem Definition in Firsthand Hint-Agent Alignment Experience over Unverified Assumptions**
  - *Rejected Framing:* Asserting as observed facts that students blindly accept AI code, systematically implement anti-patterns, and create debugging bottlenecks for mentors. Treating metrics (hint deletion, debugging loops) as established proof rather than methods of investigation.
  - *Adopted Position:* The core problem is the **Intent-and-Context Alignment Gap** — specifically that repository context alone may not fully capture what a student intends to build next, leading agents to provide guidance that may be plausible in isolation but fails to match the student's intended design direction. Metrics like hint deletion and context-correction messages are hypotheses and evaluation methods to be investigated, not pre-existing facts at scale.

### Product & Value Proposition

- 🔵 **Strong Stance: Selective Interaction Mechanism over Heavy Intent Schemas & Universal Verification**
  - *Rejected Framing:* Defining the product as a general-purpose "AI coding mentor", forcing rigid intent files (`architecture-intent.md`), claiming active verification is "strictly required" over other context approaches, or requiring intent-verification prompts before *every* single query regardless of complexity.
  - *Adopted Position:* Focus strictly on the **Selective Intent-Verification Layer** (an interaction mechanism), recognized as one promising approach among several to bridge the gap between existing codebase state and intended design direction. Intent verification should occur conditionally—specifically when queries depend on architectural or project-specific context that the agent might misunderstand—while straightforward queries receive direct answers. The mechanism relies on lightweight conversational assumption checks rather than heavy schema files.

### Unique Differentiation
